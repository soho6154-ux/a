<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💖 Tyhira, Will You Be My Valentine? 💖</title>
<style>
/* ===== Global Styles ===== */
* { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', sans-serif; }
body {
  background: linear-gradient(to bottom, #ffe6e6, #ffcccc);
  display:flex; justify-content:center; align-items:center;
  height:100vh; overflow:hidden; text-align:center; position:relative;
  padding: 10px;
}
h1 {
  font-size:2rem; color:#e60073; margin-bottom:20px;
  text-shadow: 1px 1px 4px #ff99cc;
}

/* ===== Button ===== */
button {
  background-color:#ff66b3; border:none; color:white;
  padding:12px 25px; font-size:1rem; border-radius:25px;
  cursor:pointer; transition:0.3s; box-shadow:0 4px 8px rgba(0,0,0,0.2);
}
button:hover { background-color:#ff3399; }
button.pulse { animation: pulse 1.5s infinite; }
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.08); }
}

/* ===== Love Letter ===== */
#loveLetter {
  display:none; margin-top:20px; max-width:95vw;
  background-color:#fff0f5; padding:20px;
  border-radius:20px; box-shadow:0 6px 12px rgba(0,0,0,0.3);
  font-size:1rem; line-height:1.5;
  animation: fadeIn 1.5s forwards;
  word-break: break-word;
}
@keyframes fadeIn { from {opacity:0; transform: translateY(10px);} to {opacity:1; transform: translateY(0);} }

/* ===== Flowers ===== */
#flowers { position:fixed; bottom:0; left:0; width:100%; height:0; pointer-events:none; }
.flower {
  position:absolute; width:20px; height:20px;
  background-image:url('https://i.postimg.cc/TwZ7VbV2/flower.png');
  background-size:cover; animation: fall linear infinite;
}
@keyframes fall {
  0% { transform: translateY(0) rotate(0deg); }
  100% { transform: translateY(100vh) rotate(360deg); }
}

/* ===== Floating Hearts ===== */
.heart {
  position:absolute; width:18px; height:18px;
  background-image:url('https://i.postimg.cc/7Z4wK6Ys/heart.png');
  background-size:cover; animation: floatHeart linear infinite;
  opacity:0.8;
}
@keyframes floatHeart {
  0% { transform: translateY(0) translateX(0) rotate(0deg); }
  100% { transform: translateY(-100vh) translateX(20px) rotate(360deg); }
}

/* ===== Responsive for Mobile ===== */
@media(max-width:480px){
  h1 { font-size:1.5rem; }
  button { padding:10px 20px; font-size:0.95rem; }
  #loveLetter { font-size:0.9rem; padding:15px; }
  .flower { width:15px; height:15px; }
  .heart { width:14px; height:14px; }
}
</style>
</head>
<body>

<div>
  <h1>💖 Tyhira, Will You Be My Valentine? 💖</h1>
  <button id="showLetter" class="pulse">Open Your Love Letter 💌</button>
  
  <div id="loveLetter">
    <p>My dearest Tyhira,</p>
    <p>From the moment we met, my heart knew you were someone extraordinary. Every laugh, every glance, every moment with you makes my world brighter. You are my sun on cloudy days, my warmth in the cold, and my home wherever I am.</p>
    <p>I can’t imagine a life without your smile, your kindness, and your love. You inspire me to be better every day, and I want to share all my dreams, hopes, and endless moments with you.</p>
    <p>Tyhira, will you make me the happiest person alive and be my Valentine? ❤️</p>
    <p>Forever yours, 💖</p>
  </div>
</div>

<!-- Animation Containers -->
<div id="flowers"></div>
<div id="hearts"></div>

<!-- Optional Background Music -->
<audio id="bgMusic" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<script>
// ===== Elements =====
const showLetterBtn = document.getElementById('showLetter');
const loveLetter = document.getElementById('loveLetter');
const flowersContainer = document.getElementById('flowers');
const heartsContainer = document.getElementById('hearts');
const bgMusic = document.getElementById('bgMusic');

// ===== Show Love Letter =====
showLetterBtn.addEventListener('click', () => {
  loveLetter.style.display = 'block';
  launchFlowers();
  launchHearts();
  bgMusic.play().catch(()=>{}); // Play music if allowed
});

// ===== Launch Flowers =====
function launchFlowers() {
  for(let i=0; i<25; i++){
    const flower = document.createElement('div');
    flower.classList.add('flower');
    flower.style.left = Math.random() * 100 + 'vw';
    flower.style.animationDuration = (Math.random()*3 + 2) + 's';
    flowersContainer.appendChild(flower);
    setTimeout(()=>flower.remove(), 5000);
  }
}

// ===== Launch Floating Hearts =====
function launchHearts() {
  for(let i=0; i<20; i++){
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.animationDuration = (Math.random()*4 + 3) + 's';
    heartsContainer.appendChild(heart);
    setTimeout(()=>heart.remove(), 7000);
  }
}
</script>
</body>
</html>
