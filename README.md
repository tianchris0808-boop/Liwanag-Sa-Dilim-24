<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Liwanag sa Dilim</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Inter:wght@300;400&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background: black;
  color: #f5d76e;
  text-align: center;
}

a { text-decoration: none; }

canvas {
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
}

/* 🌟 LOADER */
#loader {
  position: fixed;
  width: 100%;
  height: 100%;
  background: black;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  z-index: 9999;
  transition: opacity 1.5s ease;
}

.lamp {
  width: 40px;
  height: 80px;
  background: #f5d76e22;
  border-radius: 10px;
  position: relative;
  box-shadow: 0 0 40px #f5d76e33;
}

.flame {
  width: 18px;
  height: 30px;
  background: radial-gradient(circle, #fff7c2 0%, #f5d76e 60%, transparent 80%);
  border-radius: 50%;
  position: absolute;
  top: -25px;
  left: 50%;
  transform: translateX(-50%);
  animation: flicker 1.2s infinite;
}

@keyframes flicker {
  0% { transform: translateX(-50%) scale(1); opacity: 0.8; }
  50% { transform: translateX(-50%) scale(1.3); opacity: 1; }
  100% { transform: translateX(-50%) scale(1); opacity: 0.8; }
}

.loader-text {
  margin-top: 30px;
  font-family: 'Playfair Display', serif;
  font-size: 24px;
  opacity: 0;
  animation: fadeText 3s forwards;
}

@keyframes fadeText {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

/* 🌌 SECTIONS */
.section {
  max-width: 750px;
  margin: auto;
  padding: 70px 20px;
}

.page {
  display: none;
  opacity: 0;
  transform: translateY(20px);
}

.page.active {
  display: block;
  animation: fadeIn 0.6s forwards;
}

@keyframes fadeIn {
  to { opacity: 1; transform: translateY(0); }
}

h1,h2 {
  font-family: 'Playfair Display', serif;
}

.divider {
  width: 60px;
  height: 1px;
  background: #f5d76e55;
  margin: 20px auto;
}

.button {
  display:block;
  margin:10px auto;
  padding:14px;
  max-width:280px;
  border-radius:999px;
  background:#f5d76e;
  color:black;
  font-weight:bold;
  border:none;
  cursor:pointer;
  transition:0.3s;
}

.button:hover {
  transform:scale(1.05);
}

/* ✨ PRAYER STYLE */
.prayer {
  margin-top:20px;
  padding:20px;
  border:1px solid #f5d76e33;
  border-radius:10px;
  line-height:1.7;
  text-align:left;
}
</style>
</head>

<body>

<!-- 🌟 LOADER -->
<div id="loader">
  <div class="lamp">
    <div class="flame"></div>
  </div>
  <div class="loader-text">Liwanag sa Dilim</div>
</div>

<canvas id="stars"></canvas>

<!-- MAIN -->
<div id="main" class="page active">

<section class="section">
  <h1>Liwanag sa Dilim</h1>
  <p>Light in the Darkness</p>
  <div class="divider"></div>
  <p>You’ve always been a beacon of light in dark times; may I be one for you?</p>

  <button class="button" onclick="toggleMusic()">🎵 Play Music</button>
</section>

<section class="section">
  <h2>About</h2>
  <div class="divider"></div>
  <p>This program seeks to provide an integration of psychoeducation, emotional, and social support services in one space that is ethical and professional.</p>
</section>

<section class="section">
  <h2>Explore</h2>
  <div class="divider"></div>

  <button class="button" onclick="showPage('faith')">✨ A Faithful Reminder</button>

  <button class="button" onclick="toggle('vent')">💬 A Wall for Everyone</button>
  <div id="vent" style="display:none;">
    <a class="button" href="https://sendthesong.xyz/" target="_blank">Go to Vent Out</a>
  </div>
</section>

<section class="section">
  <h2>Contacts</h2>
  <div class="divider"></div>
  <a class="button" href="https://www.facebook.com/share/14bbKGnjKSy/" target="_blank">📘 Facebook</a>
</section>

<section class="section">
  <a class="button" href="https://docs.google.com/forms/d/e/1FAIpQLSeW0-n0nv7i5IJUhf__ZEx_vHCW-UCzvL6TuHghYUBWwaKKlg/viewform" target="_blank">
    ⭐ Rate Us
  </a>
</section>

</div>

<!-- FAITH PAGE -->
<div id="faith" class="page">
<section class="section">
  <h2>A Faithful Reminder</h2>

  <button class="button" onclick="showPage('joy')">🙏 Prayer for Joy</button>
  <button class="button" onclick="showPage('light')">💛 Prayer for a Lighter Heart</button>
  <button class="button" onclick="showPage('after')">🌅 Prayer After a Hard Season</button>

  <button class="button" onclick="showPage('main')">⬅ Back</button>
</section>
</div>

<!-- PRAYER: JOY -->
<div id="joy" class="page">
<section class="section">
<h2>Prayer for Joy</h2>
<div class="prayer">
<strong>A Prayer for Joy in the Ordinary</strong><br><br>
Lord, open my eyes to the beauty hiding in ordinary days. Let me find happiness in small things — a kind word, a quiet morning, a moment of peace. Remind me that a simple life, lived with gratitude, is a rich one. Amen.
</div>
<button class="button" onclick="showPage('faith')">⬅ Back</button>
</section>
</div>

<!-- PRAYER: LIGHT -->
<div id="light" class="page">
<section class="section">
<h2>Prayer for a Lighter Heart</h2>
<div class="prayer">
<strong>A Prayer for a Lighter Heart</strong><br><br>
God, I have been carrying so much. Worry, regret, anxiety, disappointment. Today I lay it all down at Your feet. Replace the heaviness in my chest with something lighter — with hope, with laughter, with the quiet joy of knowing I am not alone. Amen.
</div>
<button class="button" onclick="showPage('faith')">⬅ Back</button>
</section>
</div>

<!-- PRAYER: AFTER -->
<div id="after" class="page">
<section class="section">
<h2>Prayer After a Hard Season</h2>
<div class="prayer">
<strong>A Prayer After a Hard Season</strong><br><br>
Father, it has been a long and difficult road. I am tired in ways I cannot fully explain. But I believe that joy comes in the morning, and I am asking You — let my morning come. Restore what has been lost. Renew what has grown weary. Amen.
</div>
<button class="button" onclick="showPage('faith')">⬅ Back</button>
</section>
</div>

<!-- AUDIO -->
<audio id="bgMusic" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/10/25/audio_946e7c9c4d.mp3" type="audio/mpeg">
</audio>

<script>
function toggle(id){
  const el = document.getElementById(id);
  el.style.display = el.style.display === "block" ? "none" : "block";
}

function showPage(id){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}

function toggleMusic(){
  const music = document.getElementById("bgMusic");
  if(music.paused){
    music.volume = 0.6;
    music.play();
  } else {
    music.pause();
  }
}

/* 🎬 LOADER */
window.addEventListener("load", ()=>{
  setTimeout(()=>{
    const loader = document.getElementById("loader");
    loader.style.opacity = "0";
    setTimeout(()=>loader.style.display="none",1500);
  },2500);
});

/* 🌠 STARS */
const canvas = document.getElementById("stars");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let stars = Array(120).fill().map(()=>({
  x: Math.random()*canvas.width,
  y: Math.random()*canvas.height,
  size: Math.random()*2,
  opacity: Math.random()
}));

function drawStars(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  stars.forEach(s=>{
    s.opacity += (Math.random()-0.5)*0.05;
    ctx.fillStyle = `rgba(245,215,110,${s.opacity})`;
    ctx.fillRect(s.x,s.y,s.size,s.size);
  });
  requestAnimationFrame(drawStars);
}
drawStars();
</script>

</body>
</html>
