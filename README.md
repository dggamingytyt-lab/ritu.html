<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💌</title>

<style>
body{
  margin:0;
  height:100vh;
  overflow:hidden;
  display:flex;
  justify-content:center;
  align-items:center;
  background:linear-gradient(135deg,#ffb6c1,#ffc0cb,#ffd1dc,#ffe4ec);
  font-family:Arial, sans-serif;
}

/* Envelope */
#envelope{
  font-size:95px;
  cursor:pointer;
  animation:float 1.6s ease-in-out infinite;
  text-shadow:0 0 20px #ff1493;
  z-index:10;
}

@keyframes float{
  0%{transform:translateY(0);}
  50%{transform:translateY(-18px);}
  100%{transform:translateY(0);}
}

/* Popup */
#popup{
  position:fixed;
  inset:0;
  background:rgba(255,182,193,0.6);
  display:none;
  justify-content:center;
  align-items:center;
  z-index:20;
}

.box{
  background:#fff0f5;
  padding:28px;
  border-radius:22px;
  max-width:360px;
  text-align:center;
  animation:pop 0.8s ease;
  box-shadow:0 0 40px rgba(255,20,147,0.6);
}

@keyframes pop{
  from{transform:scale(0.6); opacity:0;}
  to{transform:scale(1); opacity:1;}
}

.box h2{ color:#ff1493; }

.box p{
  font-size:15.5px;
  line-height:1.7;
  color:#444;
}

/* Falling petals */
.petal{
  position:absolute;
  top:-30px;
  font-size:24px;
  animation:fall linear infinite;
  opacity:0.9;
}

@keyframes fall{
  to{
    transform:translateY(120vh) rotate(720deg);
  }
}

/* Floating hearts */
.heart{
  position:absolute;
  font-size:22px;
  animation:floatUp 3.5s linear forwards;
}

@keyframes floatUp{
  to{
    transform:translateY(-160px) scale(1.3);
    opacity:0;
  }
}

/* Sparkles */
.sparkle{
  position:absolute;
  width:7px;
  height:7px;
  background:#fff;
  border-radius:50%;
  box-shadow:0 0 15px #ff1493;
  animation:spark 0.9s ease-out forwards;
}

@keyframes spark{
  to{
    transform:scale(4);
    opacity:0;
  }
}
</style>
</head>

<body>

<div id="envelope" onclick="openMsg()">💌</div>

<div id="popup">
  <div class="box">
    <h2>Dear RITU ❤️</h2>
    <p>
      I think I’m not the best for you 🥺💗,<br>
      but you are truly special to me 🌸✨.<br><br>

      I don’t know when it started ⏳💭,<br>
      but your name feels soft 🌷💞,<br>
      your presence feels calm 😌🌼,<br>
      and your smile feels warm ☀️😊.<br><br>

      This is not pressure 🚫😇,<br>
      not expectations 🙏💫,<br>
      just honesty from my heart 💖🫶.<br><br>

      Somewhere out there 🌍💭,<br>
      someone silently wishes you happiness 🍀💝,<br>
      smiles a little thinking of you 😊💓,<br>
      and hopes life always treats you kindly 🌈🤍.<br><br>

      No matter what happens ⏳✨,<br>
      I hope you stay the same 💐🌟,<br>
      simple, strong, and beautiful 💖🌸.<br><br>

      And if someday you allow me 🥹💞,<br>
      I want you to be mine ❤️🌹.
    </p>
  </div>
</div>

<script>
function openMsg(){
  document.getElementById("popup").style.display="flex";
}

/* Heavy falling petals */
setInterval(()=>{
  for(let i=0;i<2;i++){
    const p=document.createElement("div");
    p.className="petal";
    p.innerHTML="🌸";
    p.style.left=Math.random()*100+"vw";
    p.style.animationDuration=4+Math.random()*4+"s";
    document.body.appendChild(p);
    setTimeout(()=>p.remove(),9000);
  }
},300);

/* Touch effects */
document.addEventListener("click",e=>{
  for(let i=0;i<3;i++){
    const h=document.createElement("div");
    h.className="heart";
    h.innerHTML="💖";
    h.style.left=e.clientX+Math.random()*20+"px";
    h.style.top=e.clientY+Math.random()*20+"px";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),3500);
  }

  for(let i=0;i<8;i++){
    const s=document.createElement("div");
    s.className="sparkle";
    s.style.left=e.clientX+Math.random()*25+"px";
    s.style.top=e.clientY+Math.random()*25+"px";
    document.body.appendChild(s);
    setTimeout(()=>s.remove(),900);
  }
});
</script>

</body>
</html>
