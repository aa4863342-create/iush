<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Aashika 🎂</title>

<style>
  body {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
    height: 100vh;
    background: linear-gradient(135deg, #ffafbd, #ffc3a0, #ffd1dc);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
  }

  body::before {
    content: "";
    position: fixed;
    inset: 0;
    background: rgba(255, 255, 255, 0.35);
    backdrop-filter: blur(15px);
    z-index: -1;
  }

  .box {
    background: rgba(255, 255, 255, 0.92);
    padding: 35px;
    border-radius: 22px;
    text-align: center;
    max-width: 440px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    animation: fadeIn 1.2s ease;
    z-index: 2;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(25px); }
    to { opacity: 1; transform: translateY(0); }
  }

  h1 {
    margin-top: 0;
    color: #c9184a;
  }

  p {
    color: #444;
    line-height: 1.6;
    white-space: pre-wrap;
  }

  button {
    padding: 12px 26px;
    margin: 10px;
    font-size: 1em;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    background: linear-gradient(135deg, #ff758f, #ffb3c1);
    color: #222;
    transition: transform 0.2s;
  }

  button:hover {
    transform: scale(1.08);
  }

  .hidden {
    display: none;
  }

  .bouquet {
    font-size: 90px;
    cursor: pointer;
    animation: float 2s infinite alternate;
  }

  @keyframes float {
    from { transform: translateY(0); }
    to { transform: translateY(-15px); }
  }

  .countdown {
    font-size: 6rem;
    font-weight: bold;
    color: #c9184a;
  }

  /* ❤️ Floating hearts */
  .heart {
    position: fixed;
    bottom: -20px;
    font-size: 24px;
    animation: floatUp linear forwards;
    pointer-events: none;
    z-index: 1;
  }

  @keyframes floatUp {
    from { transform: translateY(0); opacity: 1; }
    to { transform: translateY(-110vh); opacity: 0; }
  }
</style>
</head>

<body>

<!-- PAGE 1 -->
<div id="page1" class="box">
  <h1>Is today January 1st? 🌸</h1>
  <button onclick="goYes()">Yes!</button>
  <button onclick="alert('Hmm 🤔 try again')">No?</button>
</div>

<!-- PAGE 2 -->
<div id="page2" class="box hidden">
  <h1>For you, Aashika 💖</h1>
  <p>Tap the bouquet</p>
  <div class="bouquet" onclick="startCountdown()">💐</div>
</div>

<!-- PAGE 3 -->
<div id="page3" class="box hidden">
  <div id="countdown" class="countdown">10</div>
</div>

<!-- PAGE 4 -->
<div id="page4" class="box hidden">
  <h1>Happy Birthday Aashika 🎂✨</h1>
  <p id="typeText"></p>
</div>

<script>
  function goYes() {
    page1.classList.add("hidden");
    page2.classList.remove("hidden");
  }

  function startCountdown() {
    page2.classList.add("hidden");
    page3.classList.remove("hidden");

    let count = 10;
    countdown.textContent = count;

    const timer = setInterval(() => {
      count--;
      if (count > 0) {
        countdown.textContent = count;
      } else {
        clearInterval(timer);
        page3.classList.add("hidden");
        page4.classList.remove("hidden");
        typeWriter();
      }
    }, 1000);
  }

  const text = `aka Dalli 🌸

I hope today makes you feel truly special and appreciated 💫
You have such a kind and beautiful energy that naturally draws people toward you,
and I feel lucky to know you 💛😊

May this year bring you happiness, confidence,
and moments that make you smile without even trying 🌟🌼
Never forget how amazing you are 💖🌷

Wishing you a birthday full of warmth,
joy, and beautiful memories 🎁🎉`;

  let i = 0;
  function typeWriter() {
    if (i < text.length) {
      typeText.textContent += text.charAt(i);
      i++;
      setTimeout(typeWriter, 35);
    }
  }

  /* ❤️ Hearts */
  function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.textContent = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (4 + Math.random() * 4) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 8000);
  }

  setInterval(createHeart, 500);
</script>

</body>
</html>
