<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@700&display=swap');

    body {
      background-color: black;
      margin: 0;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
    }

    .container {
      text-align: center;
      position: relative;
      z-index: 10;
    }

    .letter {
      display: inline-block;
      font-size: 6em; /* Made text a bit larger */
      font-family: 'Poppins', sans-serif;
      font-weight: bold;
      color: navy;
      text-shadow: 0 0 15px navy, 0 0 30px navy, 0 0 45px navy;
      opacity: 0;
      animation: fadeIn 1s forwards;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    .small-text {
      font-size: 2em;
      font-family: 'Great Vibes', cursive;
      color: navy;
      text-shadow: 0 0 10px navy, 0 0 20px navy;
      margin-top: 10px;
      animation: fadeIn 2s forwards;
    }

    /* Fireworks animation */
    .firework {
      position: absolute;
      width: 3px;
      height: 3px;
      background-color: navy;
      border-radius: 50%;
      opacity: 0;
      animation: explode 1.5s ease-out infinite;
      pointer-events: none; /* Ensure fireworks don’t block other content */
    }

    @keyframes explode {
      0% {
        transform: scale(0.1);
        opacity: 1;
      }
      70% {
        opacity: 1;
      }
      100% {
        transform: scale(3);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <audio id="birthdaySong" autoplay>
    <source src="https://drive.google.com/uc?export=download&id=1F37Ab1t6Tifxo_4skqoTjlCpPDaeHxHA" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <div class="container">
    <div>
      <span class="letter" style="animation-delay: 0s;">H</span>
      <span class="letter" style="animation-delay: 0.2s;">a</span>
      <span class="letter" style="animation-delay: 0.4s;">p</span>
      <span class="letter" style="animation-delay: 0.6s;">p</span>
      <span class="letter" style="animation-delay: 0.8s;">y</span>
      <br>
      <span class="letter" style="animation-delay: 1s;">B</span>
      <span class="letter" style="animation-delay: 1.2s;">i</span>
      <span class="letter" style="animation-delay: 1.4s;">r</span>
      <span class="letter" style="animation-delay: 1.6s;">t</span>
      <span class="letter" style="animation-delay: 1.8s;">h</span>
      <span class="letter" style="animation-delay: 2s;">d</span>
      <span class="letter" style="animation-delay: 2.2s;">a</span>
      <span class="letter" style="animation-delay: 2.4s;">y</span>
    </div>
    <div class="small-text">
      Sweet Seventeen Ahmed
    </div>
  </div>

  <!-- Fireworks -->
  <div id="animations"></div>

  <script>
    // Play audio when the page loads
    const audio = document.getElementById('birthdaySong');
    audio.volume = 0.5;

    // Create fireworks
    const animationsContainer = document.getElementById('animations');

    // Generate Fireworks
    function createFirework() {
      const firework = document.createElement('div');
      firework.className = 'firework';
      firework.style.left = ${Math.random() * 100}%;
      firework.style.top = ${Math.random() * 100}%;
      animationsContainer.appendChild(firework);

      // Remove firework after animation
      setTimeout(() => {
        animationsContainer.removeChild(firework);
      }, 1500);
    }

    // Generate fireworks at intervals
    setInterval(createFirework, 300);
  </script>
</body>
</html>