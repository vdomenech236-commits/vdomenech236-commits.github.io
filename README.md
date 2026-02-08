<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Pour toi ❤️</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  font-family: Arial, sans-serif;
}

#box {
  background: white;
  padding: 30px;
  border-radius: 20px;
  text-align: center;
  z-index: 2;
}

button {
  font-size: 22px;
  padding: 12px 30px;
  border: none;
  border-radius: 15px;
  background: #ff4d6d;
  color: white;
}

#love {
  display: none;
  font-size: 70px;
  color: #ff1e56;
  font-weight: bold;
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.1); }
  100% { transform: scale(1); }
}

.heart {
  position: fixed;
  top: -10px;
  font-size: 24px;
  animation: fall linear forwards;
}

@keyframes fall {
  to {
    transform: translateY(110vh);
  }
}
</style>
</head>

<body>

<div id="box">
  <h1>Tu veux être ma Saint-Valentin ? 💘</h1>
  <p id="msg"></p>
  <button onclick="yes()">Oui 💖</button>
</div>

<div id="love">JE T’AIME ❤️</div>

<script>
let count = 0;
const msgs = [
  "Oups 😅",
  "Encore un bug 🙈",
  "Ça veut pas 😳",
  "Dernier essai 🤞"
];

function yes() {
  count++;
  if (count < 5) {
    document.getElementById("msg").innerText = msgs[count - 1];
  } else {
    document.getElementById("box").style.display = "none";
    document.getElementById("love").style.display = "block";
    hearts();
  }
}

function hearts() {
  setInterval(() => {
    const h = document.createElement("div");
    h.className = "heart";
    h.innerText = "❤️";
    h.style.left = Math.random() * 100 + "vw";
    h.style.animationDuration = (2 + Math.random() * 3) + "s";
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 5000);
  }, 300);
}
</script>

</body>
</html>
