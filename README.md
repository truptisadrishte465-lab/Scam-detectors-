<!DOCTYPE html>
<html>
<head>
  <title>Scam Link Detector</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 30px;
      background: #f4f4f9;
    }
    h1 {
      color: #333;
    }
    input {
      width: 80%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    #result {
      margin-top: 20px;
      font-weight: bold;
      word-wrap: break-word;
    }
  </style>
</head>
<body>
  <h1>Scam Link Detector</h1>
  <p>Enter a link below to check if it looks suspicious:</p>
  
  <input type="text" id="urlInput" placeholder="Enter website link">
  <br>
  <button onclick="checkLink()">Check</button>
  
  <div id="result"></div>

  <script>
    function checkLink() {
      let url = document.getElementById("urlInput").value.trim();
      let result = document.getElementById("result");

      if (!url) {
        result.innerHTML = "❌ Please enter a link first.";
        result.style.color = "black";
        return;
      }

      // Convert to lowercase for case-insensitive check
      url = url.toLowerCase();

      // List of suspicious keywords
      const suspiciousKeywords = [
        "free-money", "click-here", "win-prize", "bonus", "claim-now", "urgent"
      ];

      let isSuspicious = suspiciousKeywords.some(keyword => url.includes(keyword));

      if (isSuspicious) {
        result.innerHTML = "⚠️ This link looks suspicious!";
        result.style.color = "red";
      } else {
        result.innerHTML = "✅ This link looks safe (basic check).";
        result.style.color = "green";
      }
    }
  </script>
</body>
</html># Scam-detectors-
