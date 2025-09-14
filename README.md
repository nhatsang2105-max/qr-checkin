<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Quét mã QR điểm danh</title>
  <script src="https://unpkg.com/html5-qrcode@2.3.8/html5-qrcode.min.js"></script>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    #qr-reader { width: 300px; margin: auto; }
    #result { margin-top: 20px; font-size: 18px; color: green; }
  </style>
</head>
<body>
  <h2>Quét mã QR để điểm danh</h2>
  <div id="qr-reader"></div>
  <div id="result"></div>

  <script>
    function onScanSuccess(decodedText, decodedResult) {
      document.getElementById("result").innerText = "Mã quét: " + decodedText;

      fetch("https://script.google.com/macros/s/AKfycbx_MZFnsojepfa2c3wtHKL6mKPOwsw05jAw4rVPHDLhVguX_ymNatgI86QCNILpipY/exec", {
        method: "POST",
        body: JSON.stringify({ code: decodedText }),
        headers: { "Content-Type": "application/json" }
      })
      .then(res => res.json())
      .then(data => {
        alert(data.message || "Điểm danh thành công!");
      })
      .catch(err => {
        alert("Lỗi gửi mã: " + err);
      });
    }

    function onScanFailure(error) {
      // không cần xử lý lỗi nhỏ
    }

    const qrScanner = new Html5QrcodeScanner("qr-reader", {
      fps: 10,
      qrbox: 250
    });

    qrScanner.render(onScanSuccess, onScanFailure);
  </script>
</body>
</html>
