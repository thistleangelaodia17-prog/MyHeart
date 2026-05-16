# MyHeart
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Pulsating Heart with Particles</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: #111;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    #particles-js {
      position: absolute;
      width: 100%;
      height: 100%;
      z-index: 0;
    }

    .heart {
      position: relative;
      width: 100px;
      height: 90px;
      background: red;
      transform: rotate(-45deg);
      animation: pulse 1s infinite;
      z-index: 1;
      box-shadow: 0 0 30px hotpink, 0 0 60px purple;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 100px;
      height: 90px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -50px;
      left: 0;
    }

    .heart::after {
      left: 50px;
      top: 0;
    }

    @keyframes pulse {
      0%   { transform: rotate(-45deg) scale(1); }
      50%  { transform: rotate(-45deg) scale(1.2); }
      100% { transform: rotate(-45deg) scale(1); }
    }
  </style>
</head>
<body>
  <!-- Particle background -->
  <div id="particles-js"></div>

  <!-- Heart -->
  <div class="heart"></div>

  <!-- Background music -->
  <audio autoplay loop>
    <!-- Replace with the actual path to your file -->
    <source src="lief.mp3" type="audio/mpeg">
  </audio>

  <!-- Particle library -->
  <script src="https://cdn.jsdelivr.net/npm/particles.js"></script>
  <script>
    particlesJS("particles-js", {
      particles: {
        number: { value: 80 },
        size: { value: 3 },
        move: { speed: 2 },
        line_linked: { enable: false },
        color: { value: "#ff69b4" }
      },
      interactivity: {
        events: {
          onhover: { enable: true, mode: "repulse" }
        }
      }
    });
  </script>
</body>
</html>
