<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Điểm danh QR</title>
  <script src="https://unpkg.com/html5-qrcode@2.3.7/minified/html5-qrcode.min.js"></script>
  <style>
    #reader { width: 400px; margin: auto; }
    #result { text-align: center; margin-top: 20px; font-size: 1.2em; }
  </style>
</head>
<body>
  <h2 style="text-align:center">Quét mã QR để điểm danh</h2>
  <div id="reader"></div>
  <div id="result">Chưa quét.</div>

  <script>
    const apiUrl = 'https://script.google.com/macros/s/AKfycbzhTf9tS_3J4Rkp34CrQQPugxp9eHLNk75CHmU-hSqP1ml-UmnNKS495CBjFogWXMoy/exec';  // dán Web app URL ở bước 3

    function onScanSuccess(decodedText) {
      html5QrcodeScanner.clear();
      document.getElementById('result').innerText = 'Đang gửi mã...';

      fetch(`${apiUrl}?code=${encodeURIComponent(decodedText)}`)
        .then(res => res.json())
        .then(data => {
          document.getElementById('result').innerText = data.message;
        })
        .catch(err => {
          console.error(err);
          document.getElementById('result').innerText = 'Lỗi kết nối server.';
        });
    }

    const html5QrcodeScanner = new Html5QrcodeScanner(
      "reader", { fps: 10, qrbox: 250 }
    );
    html5QrcodeScanner.render(onScanSuccess);
  </script>
</body>
</html>
