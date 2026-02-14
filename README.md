<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Valentine Special ❤️</title>
<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  overflow-x: hidden;
  text-align: center;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  animation: bgMove 10s infinite alternate;
}

@keyframes bgMove {
  from {background-position: left;}
  to {background-position: right;}
}

h1 {
  font-size: 3em;
  margin-top: 100px;
  color: white;
  animation: glow 2s infinite alternate;
}

@keyframes glow {
  from {text-shadow: 0 0 10px #fff;}
  to {text-shadow: 0 0 30px #ff0066;}
}

button {
  padding: 12px 25px;
  margin: 10px;
  font-size: 18px;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.1);
}

.hidden { display: none; }

.heart {
  position: fixed;
  color: red;
  font-size: 24px;
  animation: float 4s linear infinite;
}

@keyframes float {
  0% { transform: translateY(0); opacity:1;}
  100% { transform: translateY(-800px); opacity:0;}
}

.sparkle {
  animation: sparkle 1s infinite alternate;
}

@keyframes sparkle {
  from {text-shadow: 0 0 5px white;}
  to {text-shadow: 0 0 20px yellow;}
}

.teddy {
  font-size: 100px;
  animation: bounce 1s infinite alternate;
}

@keyframes bounce {
  from {transform: translateY(0);}
  to {transform: translateY(-20px);}
}
</style>
</head>

<body>

<h1 id="mainText">Hi My Beautiful Wifey 💖</h1>
<button id="startBtn" onclick="startLove()">Click Here To Continue</button>

<div id="question1" class="hidden">
  <h2 class="sparkle">I need to ask you something... Can I ask it? ✨</h2>
  <button onclick="askValentine()">Yes</button>
  <button onclick="noFirst()">No</button>
</div>

<div id="question2" class="hidden">
  <h2 class="sparkle">Babee will you be my Valentine? 💕</h2>
  <button onclick="yesValentine()">Yes</button>
  <button onclick="noValentine()">No</button>
</div>

<div id="finalYes" class="hidden">
  <div class="teddy">🧸🎁</div>
  <h2 class="sparkle">I have nothing for you... I am enough for you ❤️<br>
  I am the gift from God... What else you need? 💝</h2>
</div>

<div id="finalNo" class="hidden">
  <h2>😭 You can't do this to me... I am your babe 💔</h2>
  <button onclick="yesValentine()">Yes I'll be your Valentine 💖</button>
</div>

<script>
function startLove(){
  document.getElementById("startBtn").style.display="none";
  createHearts();
  setTimeout(()=>{
    document.getElementById("question1").classList.remove("hidden");
  },2000);
}

function createHearts(){
  for(let i=0;i<30;i++){
    let heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*100+"vw";
    heart.style.top="100vh";
    heart.style.animationDuration=(Math.random()*3+2)+"s";
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),4000);
  }
}

function askValentine(){
  document.getElementById("question1").classList.add("hidden");
  document.getElementById("question2").classList.remove("hidden");
}

function noFirst(){
  alert("Just kidding babee 😘 even if you say no I will ask you ❤️");
  askValentine();
}

function yesValentine(){
  document.getElementById("question2").classList.add("hidden");
  document.getElementById("finalNo").classList.add("hidden");
  document.getElementById("finalYes").classList.remove("hidden");
  createHearts();
}

function noValentine(){
  document.getElementById("question2").classList.add("hidden");
  document.getElementById("finalNo").classList.remove("hidden");
}
</script>

</body>
</html>
