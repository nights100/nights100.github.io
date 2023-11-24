
<html>
<head>
  <title>Solar</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Alex+Brush&display=swap');
    
    body {
      background-color: #000000; /* Black background */
      color: #ffffff; /* White text */
      font-family: 'Consolas', monospace; /* Consolas font for the entire body */
      opacity: 0;
      animation: fadeIn 2s forwards; /* Fading-in animation */
      text-align: center; /* Center align all text */
      overflow: hidden; /* Hide overflowing stars */
      position: relative;
      filter: blur(10px); /* Initial blur */
    }
    
    @keyframes fadeIn {
      0% {
        opacity: 0;
        filter: blur(10px); /* Start with blur */
      }
      50% {
        opacity: 0; /* Maintain opacity at 0. */
      }
      100% {
        opacity: 1;
        filter: blur(0); /* Unblur gradually */
      }
    }
    
    h1 {
      font-size: 60px;
      font-family: 'Alex Brush', cursive; /* Custom font */
      overflow: hidden;
      white-space: nowrap;
    }
    
    p {
      font-size: 18px;
      font-family: 'Alex Brush', cursive; /* Custom font */
      position: absolute;
      bottom: 0; /* Position at the bottom */
      left: 50%;
      transform: translateX(-50%);
      opacity: 0; /* Set initial opacity to 0 */
    }
    
    a {
      color: #ffffff; /* White link color */
      text-decoration: none; /* Remove underline */
    }
    
    a:hover {
      text-decoration: underline; /* Add underline on hover */
    }
    
    /* Stars animation */
    .stars {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }
    
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background-color: #ffffff;
      animation: twinkle 1s infinite;
    }
    
    @keyframes twinkle {
      0% {
        opacity: 0;
        transform: scale(0);
      }
      50% {
        opacity: 1;
        transform: scale(1);
      }
      100% {
        opacity: 0;
        transform: scale(0);
      }
    }
    
    /* Panning animation */
    .panning {
      animation: pan 30s linear infinite; /* More aggressive panning */
    }
    
    @keyframes pan {
      0% {
        background-position: 0 0;
      }
      100% {
        background-position: -200% 0; /* Increased panning distance */
      }
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
      
      setTimeout(function() {
        intro.style.transition = "opacity 2s";
        intro.style.opacity = "0";
        
        // Fade in the paragraph text
        setTimeout(function() {
          paragraph.style.color = "#ffffff"; // Set text color to white
          paragraph.style.transition = "opacity 2s";
          paragraph.style.opacity = "1";
          
          // Insert and type the additional text
          const additionalText = "Solar is a powerful discord raiding bot with a primary focus on taking down servers that promote and engage in illegal activities such as pedophilia, scams, RCTA, and furry servers. Our mission is to actively combat and put an end to these communities as they are 100% weird as hell. If you have any questions, DM 444cursed (1173054262884962377)";
          
          const additionalParagraph = document.createElement('p');
          additionalParagraph.style.fontFamily = 'Consolas, monospace'; // Set Consolas font
          additionalParagraph.style.fontSize = '18px';
          additionalParagraph.style.position = 'absolute';
          additionalParagraph.style.bottom = '50%';
          additionalParagraph.style.left = '50%';
          additionalParagraph.style.transform = 'translateX(-50%)';
          additionalParagraph.style.opacity = '0';
          body.appendChild(additionalParagraph);

          const typingEffect = setInterval(function() {
            if (additionalText.length > 0) {
              additionalParagraph.textContent += additionalText[0];
              additionalText = additionalText.slice(1);
            } else {
              clearInterval(typingEffect);
              additionalParagraph.style.transition = "opacity 2s";
              additionalParagraph.style.opacity = "1";
            }
          }, 75);
          
        }, 2000); // Wait for 2 seconds after the introduction fades out
      }, 6000);
    };
  </script>
</body>
</html>