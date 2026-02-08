<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine</title>

<style>
* {
  box-sizing: border-box;
  font-family: "Poppins", Arial, sans-serif;
}

body {
  height: 100vh;
  margin: 0;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #fff;
}

/* floating hearts background */
.heart {
  position: absolute;
  bottom: -50px;
  font-size: 20px;
  color: #f6b3c1;
  animation: floatUp linear infinite;
  opacity: 0.8;
}

@keyframes floatUp {
  from {
    transform: translateY(0) scale(1);
    opacity: 0.9;
  }
  to {
    transform: translateY(-110vh) scale(1.5);
    opacity: 0;
  }
}

.container {
  position: relative;
  z-index: 10;
  text-align: center;
  background: #ffffff;
  padding: 50px 55px;
  border-radius: 28px;
  box-shadow: 0 25px 45px rgba(244, 166, 184, 0.4);
  animation: popIn 0.6s ease;
}

@keyframes popIn {
  from {
    transform: scale(0.9);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

h1 {
  margin-bottom: 35px;
  color: #f4a6b8;
  font-size: 34px;
}

.subtitle {
  font-size: 16px;
  color: #999;
  margin-bottom: 30px;
}

button {
  padding: 15px 36px;
  font-size: 18px;
  border: none;
  border-radius: 40px;
  cursor: pointer;
  transition: all 0.2s ease;
}

#yesBtn {
  background: #f4a6b8;
  color: white;
  margin-right: 20px;
  box-shadow: 0 10px 20px rgba(244,166,184,0.4);
}

#yesBtn:hover {
  transform: scale(1.07);
}

#noBtn {
  background: #ffe6ee;
  color: #d36c8c;
  position: absolute;
}

.sparkle {
  font-size: 14px;
  margin-top: 20px;
  color: #f4a6b8;
}
</style>
</head>

<body>

<div class="container">
  <h1>Will you be my Valentine? 🤍</h1>
  <div class="subtitle">no pressure but also yes pressure</div>
  <button id="yesBtn">Yes 💗</button>
  <button id="noBtn">No 🙃</button>
  <div class="sparkle">✨ made with feelings ✨</div>
</div>

<script>
/* floating hearts generator */
const hearts = ["💗","💖","💕","💞","🤍"];

function createHeart() {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 15 + 15 + "px";
  heart.style.animationDuration = Math.random() * 3 + 4 + "s";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 7000);
}

setInterval(createHeart, 300);

/* evil no button */
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

noBtn.addEventListener("mouseover", dodge);
noBtn.addEventListener("click", dodge);

function dodge() {
  const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
  const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
}

/* yes button ending */
yesBtn.addEventListener("click", () => {
  document.body.innerHTML = `
    <div style="
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      background:#fff;
    ">
      <div style="
        background:white;
        padding:55px;
        border-radius:28px;
        text-align:center;
        box-shadow:0 25px 45px rgba(244,166,184,0.4);
        animation: popIn 0.6s ease;
      ">
        <h1 style="color:#f4a6b8;font-size:36px;">YAY 💞</h1>
        <p style="font-size:20px;color:#666;">Message me 🤍</p>
        <button onclick="window.location.href='https://instagram.com/arvinkahmed'"
          style="
            padding:15px 36px;
            font-size:18px;
            background:#f4a6b8;
            color:white;
            border:none;
            border-radius:40px;
            cursor:pointer;
            box-shadow:0 10px 20px rgba(244,166,184,0.4);
          ">
         click me
        </button>
      </div>
    </div>
  `;
});
</script>

</body>
</html>
