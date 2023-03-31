# Neon_Text_Rahul
Using HTML &amp; CSS


Shimmering text Glow
<html>
<head> 

  <title>CSS-only shimmering neon text</title>
<style>
.text-effect {
  overflow: hidden;
  position: relative;
  filter: contrast(110%) brightness(190%);
}

.neon {
  position: relative;
  background: black;
  color: transparent;
}
.neon::before, .neon::after {
  content: attr(data-text);
  color: white;
  filter: blur(0.02em);
  position: absolute;
  top: 0;
  left: 0;
  pointer-events: none;
}
.neon::after {
  mix-blend-mode: difference;
}

.gradient,
.spotlight {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  pointer-events: none;
  z-index: 10;
}

.gradient {
  background: linear-gradient(45deg, red, yellow);
  mix-blend-mode: multiply;
}

.spotlight {
  -webkit-animation: light 5s infinite linear;
          animation: light 5s infinite linear;
  background: radial-gradient(circle, white, transparent 25%) 0 0/25% 25%, radial-gradient(circle, white, black 25%) 50% 50%/12.5% 12.5%;
  top: -100%;
  left: -100%;
  mix-blend-mode: color-dodge;
}

@-webkit-keyframes light {
  100% {
    transform: translate3d(50%, 50%, 0);
  }
}

@keyframes light {
  100% {
    transform: translate3d(50%, 50%, 0);
  }
}
.neon {
  font: 700 220px "Lato", sans-serif;
  text-transform: uppercase;
  text-align: center;
  margin: 0;
}
.neon:focus {
  outline: none;
  border: 1px dotted white;
}

body {
  background: black;
  display: flex;
  min-height: 100vh;
  justify-content: center;
  align-content: center;
  align-items: center;
  overflow: hidden;
}
</style>

</head>

<body>
  <div class="text-effect">
  <!-- Select the text in the preview and type in your own -->
  <h1 class="neon" data-text="Rahul Ranjan" contenteditable>Rahul Ranjan</h1>
  <div class="gradient"></div>
  <div class="spotlight"></div>
</div>
</body>

</html>
 
