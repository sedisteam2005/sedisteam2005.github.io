<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Home + Message 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  body {
    margin:0;
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background: linear-gradient(135deg, #ffd6e8, #ffe9f1);
    font-family: 'Segoe UI', system-ui, sans-serif;
    overflow: hidden;
  }
  #house {
    font-size: 120px;
    cursor: pointer;
    text-align: center;
    position: relative;
    z-index: 10;
  }
  #content {
    display: none;
    text-align: center;
    max-width: 420px;
    padding: 20px;
    background: #fff;
    border-radius: 24px;
    box-shadow: 0 20px 40px rgba(0,0,0,.2);
    position: relative;
  }
  #messageContainer {
    height: 250px;
    overflow: hidden;
    text-align: center;
    font-size: 18px;
    line-height: 1.6;
    margin-bottom: 15px;
  }
  #message {
    display: inline-block;
    text-align: center;
  }

  /* Envelope & final message */
  #finalMessage {
    display:none;
    margin-top:20px;
    font-size:24px;
    font-weight:bold;
    color:#ff4d6d;
    text-align:center;
  }
  #envelope {
    display:none;
    font-size:80px;
    cursor:pointer;
    margin-top:15px;
  }

  /* Cute stickers */
  .sticker{
    position:absolute;
    font-size:36px;
    animation: float 4s ease-in-out infinite;
    opacity:.9;
  }

  /* Original stickers */
  .s1{ top:10px; left:10px; animation-delay:0s;}
  .s2{ top:10px; right:10px; animation-delay:1s;}
  .s3{ bottom:10px; left:14px; animation-delay:2s;}
  .s4{ bottom:12px; right:14px; animation-delay:3s;}

  /* Extra stickers */
  .s5{ top:50px; left:40%; animation-delay:0.5s;}
  .s6{ top:80px; right:30%; animation-delay:1.2s;}
  .s7{ bottom:50px; left:20%; animation-delay:0.8s;}
  .s8{ bottom:80px; right:25%; animation-delay:1.5s;}
  .s9{ top:20%; left:10%; animation-delay:2s;}
  .s10{ top:30%; right:15%; animation-delay:2.5s;}
  .s11{ bottom:25%; left:35%; animation-delay:1.8s;}
  .s12{ bottom:40%; right:40%; animation-delay:2.2s;}

  @keyframes float{
    0%,100%{ transform:translateY(0) rotate(0deg);}
    50%{ transform:translateY(-8px) rotate(3deg);}
  }
</style>
</head>
<body>

<!-- Floating stickers -->
<div class="sticker s1">💖</div>
<div class="sticker s2">🌸</div>
<div class="sticker s3">🐻</div>
<div class="sticker s4">✨</div>
<div class="sticker s5">🌈</div>
<div class="sticker s6">🍓</div>
<div class="sticker s7">🦋</div>
<div class="sticker s8">🍩</div>
<div class="sticker s9">💌</div>
<div class="sticker s10">🌟</div>
<div class="sticker s11">🐱</div>
<div class="sticker s12">🎀</div>

<div>
  <!-- House icon -->
  <div id="house">🏠</div>

  <!-- Message -->
  <div id="content">
    <div id="messageContainer">
      <div id="message">
        Sa dami ng pwedeng mangyari sa araw ko,<br>
        ikaw pa rin yung gusto kong balikan.<br>
        Kahit magulo ang mundo,<br>
        pag kausap kita, kumakalma ako.<br>
        Hindi man perfect ang lahat,<br>
        pero kapag ikaw ang kasama ko,<br>
        pakiramdam ko… nasa bahay na ako.<br>
        Ikaw ang home ko. 🏠💖<br>
        Salamat na palagi mong pinipili akong kasama,<br>
        kahit simple lang ang moments natin.<br>
        Ikaw ang pillow ko sa stress, comfort ko sa lungkot.<br>
        Alam mo, kahit minsan naaalala ko yung jokes mo,<br>
        tumatawa pa rin ako kahit mag-isa 😆<br>
        PS: Promise, hindi kita papabayaan kahit mag-out of stock ang hugs mo 😝<br>
        Kapag kasama kita, kahit traffic, ok lang.<br>
        Ikaw yung Netflix ng puso ko, hindi ko kayang i-skip.<br>
        Wala nang iba, ikaw lang ang pipiliin ko sa lahat ng seasons.<br>
        Kahit maliit lang ang moments, perfect na sila sa akin.<br>
        Salamat na pinipili mo rin ako araw-araw.<br>
        Mahal kita, at hindi kita ipagpapalit sa kahit anong pizza o milk tea 🫶<br>
        Sa bawat araw, ikaw ang dahilan ng ngiti ko at peace ng puso ko 💕
      </div>
    </div>

    <!-- Envelope & final message -->
    <div id="envelope">✉️</div>
    <div id="finalMessage">I LOVE YOUUUUUU so much love!! 💖💖💖</div>
  </div>
</div>

<script>
  const house = document.getElementById("house");
  const content = document.getElementById("content");
  const message = document.getElementById("message");
  const container = document.getElementById("messageContainer");
  const envelope = document.getElementById("envelope");
  const finalMessage = document.getElementById("finalMessage");

  house.addEventListener("click", () => {
    house.style.display = "none"; // hide house
    content.style.display = "block"; // show message

    // Auto-scroll message
    let scrollAmount = 0;
    const interval = setInterval(() => {
      scrollAmount += 1;
      container.scrollTop = scrollAmount;
      if (scrollAmount >= message.scrollHeight - container.clientHeight) {
        clearInterval(interval);

        // Show envelope and final message after scroll
        setTimeout(() => {
          envelope.style.display = "block";
          finalMessage.style.display = "block";

          // Optional: add extra floating stickers for final message
          for(let i=0;i<6;i++){
            const s = document.createElement('div');
            s.className = 'sticker';
            s.style.fontSize = '36px';
            s.style.top = Math.random()*80 + '%';
            s.style.left = Math.random()*80 + '%';
            const emojis = ['💖','🌸','✨','🌈','🍓','🦋','🎀','💌','🌟'];
            s.textContent = emojis[Math.floor(Math.random()*emojis.length)];
            document.body.appendChild(s);
          }

        }, 500); // small delay
      }
    }, 150); // scroll speed
  });
</script>

</body>
</html>
