
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>M.S.M Firecore Logo</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html, body {
      height: 100%;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #1b1b1b, #000000);
      font-family: 'Segoe UI', sans-serif;
    }

    .logo-container {
      position: relative;
      width: 340px;
      height: 200px;
      background: rgba(255, 255, 255, 0.05);
      border-radius: 16px;
      backdrop-filter: blur(12px);
      box-shadow:
        0 0 20px rgba(255, 0, 0, 0.2),
        0 0 60px rgba(255, 0, 0, 0.3),
        inset 0 0 10px rgba(255, 255, 255, 0.1);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      cursor: pointer;
      transition: 0.3s ease-in-out;
    }

    .logo-container:hover {
      transform: scale(1.05);
      box-shadow:
        0 0 25px rgba(255, 0, 0, 0.4),
        0 0 80px rgba(255, 0, 0, 0.5),
        inset 0 0 15px rgba(255, 255, 255, 0.15);
    }

    .logo-text {
      font-size: 42px;
      font-weight: bold;
      letter-spacing: 12px;
      color: white;
      z-index: 2;
      text-shadow:
        0 0 8px #ff0000,
        0 0 15px #ff1a1a,
        0 0 30px #ff3333;
      animation: pulseGlow 3s infinite ease-in-out;
    }

    .glow-frame {
      position: absolute;
      top: -2px;
      left: -2px;
      right: -2px;
      bottom: -2px;
      border-radius: 18px;
      background: linear-gradient(120deg, rgba(255,0,0,0.6), transparent, rgba(255,0,0,0.6));
      z-index: 1;
      animation: borderFlow 6s linear infinite;
      opacity: 0.3;
    }

    .reflection {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 50%;
      background: linear-gradient(to bottom, rgba(255,255,255,0.08), transparent);
      border-top-left-radius: 16px;
      border-top-right-radius: 16px;
      pointer-events: none;
    }

    @keyframes pulseGlow {
      0%, 100% {
        text-shadow:
          0 0 8px #ff0000,
          0 0 15px #ff1a1a,
          0 0 30px #ff3333;
      }
      50% {
        text-shadow:
          0 0 12px #ff1a1a,
          0 0 25px #ff3333,
          0 0 40px #ff4d4d;
      }
    }

    @keyframes borderFlow {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    /* Responsive */
    @media (max-width: 400px) {
      .logo-container {
        width: 90%;
        height: 180px;
      }

      .logo-text {
        font-size: 32px;
        letter-spacing: 8px;
      }
    }
  </style>
</head>
<body>

  <div class="logo-container" onclick="restartEffect()">
    <div class="glow-frame"></div>
    <div class="reflection"></div>
    <div class="logo-text">M.S.M</div>
  </div>

  <script>
    function restartEffect() {
      const logo = document.querySelector('.logo-text');
      logo.style.animation = 'none';
      void logo.offsetWidth;
      logo.style.animation = 'pulseGlow 3s infinite ease-in-out';
    }
  </script>

</body>
</html>

