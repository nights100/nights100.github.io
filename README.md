<html>
<head>
  <title>Solar</title>
  <style>
    /* Your existing styles */
  </style>

  <style>
    body {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    #text {
      font-size: 15px; /* Adjust the font size as needed */
      text-align: center;
    }
  </style>
</head>
<body class="panning">
  <h1 id="solar"><a href="https://example.com" target="_blank">Solar</a></h1>
  <p id="intro">Commence Retribution.</p>
  
  <div class="stars">
    <!-- Generate stars dynamically using JavaScript -->
  </div>

  <script>
    window.onload = function() {
      document.body.style.opacity = 1;
      
      const starContainer = document.querySelector('.stars');
      const heading = document.querySelector('#solar');
      const intro = document.querySelector('#intro');
      const paragraph = document.querySelector('p');
      const body = document.body;
      
      // Generate stars dynamically
      for (let i = 0; i < 100; i++) {
        const star = document.createElement('div');
        star.className = 'star';
        star.style.top = Math.random() * 100 + '%';
        star.style.left = Math.random() * 100 + '%';
        star.style.animationDelay = Math.random() * 5 + 's';
        starContainer.appendChild(star);
      }
      
      let blurAmount = 10;
      const blurInterval = setInterval(function() {
        if (blurAmount > 0) {
          document.body.style.filter = "blur(" + blurAmount + "px)";
          blurAmount -= 0.5; // Decrease blur amount in smaller increments
        } else {
          clearInterval(blurInterval);
        }
      }, 100);
      
      heading.addEventListener('click', function() {
        body.style.animation = "fadeOut 1s forwards";
        setTimeout(function() {
          body.style.background = "#000000";
          body.style.overflow = "auto";
        }, 1000);
      });

      // Your second script starts here
      var message =
        "Solar is a powerful discord raiding bot with a primary focus on taking down servers that promote and engage in illegal activities such as pedophilia, scams, RCTA, and furry servers. Our mission is to actively combat and put an end to these communities as they are 100% weird as hell. If you have any questions or concerns, DM 444cursed (1173054262884962377) on discord";
      var speed = 50; // Adjust the speed (lower values make it faster)
      var initialDelay = 3000; // Initial delay in milliseconds (3 seconds)

      var i = 0;

      function autoTyper() {
        document.getElementById("text").innerHTML += message.charAt(i);
        i++;

        if (i < message.length) {
          setTimeout(autoTyper, speed);
        }
      }

      // Start after initial delay
      setTimeout(autoTyper, initialDelay);
    };
  </script>
</body>
</html>
