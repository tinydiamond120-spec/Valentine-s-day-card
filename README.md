# Valentine-s-day-card
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RIYAH, Will You Be My Valentine? 💖</title>

  <style>
    * { box-sizing: border-box; font-family: 'Poppins', Arial, sans-serif; }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ff4d88, #ff9a9e, #fff);
      overflow: hidden;
    }

    .heart {
      position: absolute;
      width: 18px;
      height: 18px;
      background: red;
      transform: rotate(45deg);
      animation: float 6s infinite ease-in-out;
      opacity: 0.6;
    }

    .heart::before, .heart::after {
      content: "";
      position: absolute;
      width: 18px;
      height: 18px;
      background: red;
      border-radius: 50%;
    }

    .heart::before { top: -9px; left: 0; }
    .heart::after { left: -9px; top: 0; }

    @keyframes float {
      0% { transform: translateY(0) rotate(45deg); }
      50% { transform: translateY(-60px) rotate(45deg); }
      100% { transform: translateY(0) rotate(45deg); }
    }

    .card {
      background: rgba(255,255,255,0.96);
      border-radius: 26px;
      padding: 32px 24px;
      max-width: 360px;
      width: 90%;
      text-align: center;
      box-shadow: 0 20px 45px rgba(0,0,0,0.25);
      z-index: 10;
    }

    h1 { color: #e6005c; margin-bottom: 10px; }
    h2 { color: #ff3366; font-weight: 500; margin-bottom: 16px; }

    .photo {
      width: 180px;
      border-radius: 22px;
      margin: 16px auto 24px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.25);
    }

    .options { display: flex; flex-direction: column; gap: 14px; }

    button {
      padding: 14px;
      border: none;
      border-radius: 999px;
      font-size: 1rem;
      cursor: pointer;
      background: linear-gradient(135deg, #ff3366, #ff5f9e);
      color: white;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      position: relative;
    }

    button:hover {
      transform: scale(1.1);
      box-shadow: 0 12px 22px rgba(255, 51, 102, 0.45);
    }

    .footer {
      margin-top: 18px;
      font-size: 0.9rem;
      color: #ff3366;
    }

    .hidden { display: none; }
  </style>
</head>

<body>

  <!-- Floating hearts -->
  <div class="heart" style="top:10%; left:12%;"></div>
  <div class="heart" style="top:28%; left:78%; animation-delay:1s;"></div>
  <div class="heart" style="top:68%; left:20%; animation-delay:2s;"></div>
  <div class="heart" style="top:58%; left:70%; animation-delay:3s;"></div>

  <div class="card">
    <h1 id="title">RIYAH 💕</h1>
    <h2 id="question">Will you be my Valentine?</h2>

    <img src="1000032234.jpg" alt="Valentine" class="photo" />

    <div class="options" id="buttons">
      <button onclick="celebrate()">Yes 💖</button>
      <button onmouseover="runAway(this)">Obviously 😏</button>
      <button onclick="celebrate()">Yes but yessssss 💞</button>
    </div>

    <div class="footer" id="footer">Made with ❤️ just for you, Riyah</div>
  </div>

  <!-- Romantic music -->
  <audio id="music" loop>
    <source src="music.mp3" type="audio/mpeg">
  </audio>

  <!-- Confetti -->
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

  <script>
    function runAway(btn) {
      const x = Math.random() * 300 - 150;
      const y = Math.random() * 200 - 100;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function celebrate() {
      document.getElementById("question").innerText =
        "YAY!! You’re officially my Valentine 💘🥰";

      document.getElementById("buttons").classList.add("hidden");

      confetti({
        particleCount: 180,
        spread: 90,
        origin: { y: 0.6 }
      });

      document.getElementById("music").play();
    }
  </script>

</body>
</html>
