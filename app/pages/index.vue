<template>
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"
/>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet"> 
  <div class="home-page">



<div class="passport-banner">
    <span>🍺 Brewery Passport</span>
    <p>Visit all 11 breweries and discover your favorite beer.</p>
</div>
    <!-- Hero Section -->
<section class="hero-card">
  
      <div class="hero-content">
        <h1>CAMBODIAN CRAFT BEER CROWN 2026</h1>

        <p>
          Join us for Cambodia's premier craft beer competition
          featuring 11 exceptional breweries competing for the crown.
        </p>
          <a href="https://docs.google.com/forms/d/e/1FAIpQLScEjueBWitDWygOZkaHDnkADWIHhYdgZ-lH_u3EvKM2RzL1AA/viewform" class="judge-btn">Judge Here</a>
      </div>

      <div class="hero-image">
        <img src="https://i.pinimg.com/736x/20/b7/e1/20b7e12767066ccae54f28b659e84cb3.jpg" alt="Beer" />
      </div>
    </section>

    <!-- Welcome Section -->
    <section class="welcome-card">
      <h2>Welcome!</h2>

      <p>
        Thank you for being part of Cambodia Craft Beer Crown 2026.
      </p>

      <p>
        Event date: 20 July 2026 on 2:00 PM – 11:30 PM
        at Botanico Craft Beer Garden
      </p>
    </section>

    <!-- Quick Rules -->
    <section class="rules-section">
      <h2>Quick Rules</h2>

      <div class="rule">
        <div class="step-number">1</div>

        <div class="icon-box">
          <i class="fa-solid fa-beer-mug-empty"></i>
        </div>

        <h3>TASTE</h3>

        <p>Taste each beer carefully.</p>
      </div>

      <div class="arrow">⌄</div>

      <div class="rule">
        <div class="step-number">2</div>

      <div class="icon-box">
        <i class="fa-solid fa-wine-glass"></i>
      </div>

        <h3>EVALUATE</h3>

        <p>
          Consider aroma, flavor,
          balance and overall impression.
        </p>
      </div>

      <div class="arrow">⌄</div>

      <div class="rule">
        <div class="step-number">3</div>

      <div class="icon-box">
        <i class="fa-solid fa-check-to-slot"></i>
      </div>

        <h3>VOTE</h3>

        <p>
          Choose your favorite and
          submit your vote.
        </p>
      </div>
    </section>

  </div>


</template>
<style scoped>
html, body {
  font-family: 'Inter', sans-serif;
}
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body{
    background:
        linear-gradient(
            rgba(136, 87, 65, 0.88),
            rgba(255, 212, 193, 0.88)
        ),
        url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b');

    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    margin: 0%;
    min-height: 100vh;
}
.home-page {
  min-height: 100vh;
  padding: 10px 100px;
  font-family: 'Inter', sans-serif;
}
/* Navbar */

.navbar {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 12px;
}

.menu-btn {
  font-size: 32px;
  cursor: pointer;
  color: #23150f;
}

/* Hero */

.hero-card{
  background:rgba(248,240,220,.92);

  border:3px solid #C89B3C;
  border-radius:24px;

  padding:32px;

  box-shadow:
    0 15px 35px rgba(0,0,0,.25),
    inset 0 0 20px rgba(255,255,255,.4);

  backdrop-filter: blur(8px);

  display:flex;
  align-items:center;
  justify-content:space-between;

  overflow:hidden;
  position:relative;
}
.hero-card::before{
  content:"";

  position:absolute;
  top:0;
  left:0;

  width:100%;
  height:6px;

  background:
  linear-gradient(
    90deg,
    #7e2527,
    #d7a332,
    #7e2527
  );
}

.hero-content {
  flex: 1;
}
.passport-banner{
  background:#7e2527;

  color:white;

  border:2px dashed #d7a332;

  border-radius:14px;

  text-align:center;

  padding:18px;

  margin-bottom:24px;

  transform:rotate(-1deg);
}
.icon-box {
  transition: 0.3s;
}

.icon-box:hover {
  transform: scale(1.1);
  background: #5c1b1d;
  color: white;
}
.passport-banner span{
  color:#fff;
  font-size:1.4rem;
}

.passport-banner p{
  margin-top:6px;
  color:#ffffff;
}
.hero-content h1{
  font-size:35px;
  font-weight:900;
  color:#3B2417;
  line-height:1.1;
  text-transform:uppercase;
  letter-spacing:3px;
  margin-bottom:16px;
  margin: 0;
}

.hero-content p {
  font-size: 20px;
  line-height: 1.5;
  color: #2d1a10;
  margin-bottom: 35px;
}

.judge-btn{
  background:#7e2527;

  color:white;

  border:2px solid #d7a332;

  border-radius:12px;

  padding:16px 34px;

  font-size:18px;
  font-weight:700;

  cursor:pointer;

  transition:.3s;
  text-decoration: none;
}
.judge-btn:hover{
  background:#5c1b1d;

  transform:
    translateY(-3px)
    scale(1.03);
}



/* Welcome */

.welcome-card{
  background:#f8f0dc;

  border:3px solid #C89B3C;

  border-radius:20px;

  padding:30px;

  text-align:center;

  box-shadow:
    0 8px 20px rgba(0,0,0,.15);

  margin-top:24px;
}

.welcome-card h2 {
  font-size: 30px;
  margin-bottom: 10px;
}

.welcome-card p {
  font-size: 18px;
  line-height: 1.6;
}

/* Rules */

.rules-section{
  background:#f8f0dc;

  border:3px solid #C89B3C;

  border-radius:20px;

  padding:40px;

  margin-top:24px;
}
.rules-section h2 {
  text-align: center;
  font-size: 30px;
  margin-bottom: 30px;
}

.rule {
  text-align: center;
  margin-bottom: 20px;
}

.step-number{
  width:50px;
  height:50px;

  background:#C89B3C;

  border-radius:50%;

  color:white;
  font-weight:700;

  display:flex;
  align-items:center;
  justify-content:center;

  margin:auto;
}

.icon-box{
  width:70px;
  height:70px;

  border-radius:50%;

  color:#7e2527;
;

  display:flex;
  align-items:center;
  justify-content:center;

  font-size:32px;

  margin:auto;
}

.rule h3 {
  margin-top: 14px;
  font-size: 20px;
  font-weight: 700;
}

.rule p {
  margin-top: 10px;
  font-size: 16px;
  line-height: 1.6;
}

.arrow {
  text-align: center;
  color: #d7a332;
  font-size: 52px;
  margin: 8px 0;
}
.page-title{
  text-align:center;
  color:#F8E7C1;

  font-size:3.5rem;
  font-weight:800;

  text-transform:uppercase;

  text-shadow:
    0 2px 10px rgba(0,0,0,.6);

  margin-bottom:10px;
}

.divider{
  text-align:center;
  color:#C89B3C;
  font-size:1.8rem;
  margin-bottom:30px;
}
@media(min-width:768px){

.hero-content h1{
  font-size:50px;
}

}
.hero-image img{
  width:180px;

  filter:
    drop-shadow(0 10px 15px rgba(0,0,0,.3));

  animation: floatBeer 4s ease-in-out infinite;
}

@keyframes floatBeer{

  0%,100%{
    transform:translateY(0);
  }

  50%{
    transform:translateY(-12px);
  }

}
@media(min-width:768px){

.rules-section{
  display:flex;
  justify-content:space-between;
  align-items:flex-start;
  gap:30px;
}

.arrow{
  display:none;
}

.rule{
  flex:1;
}

}
/* ===========================
   Mobile Responsive
   =========================== */

@media (max-width: 768px) {

  .home-page {
    padding: 20px;
  }

  /* Hero */

  .hero-card {
    flex-direction: column-reverse;
    text-align: center;
    padding: 24px;
    gap: 24px;
  }

  .hero-content h1 {
    font-size: 32px;
    letter-spacing: 1px;
  }

  .hero-content p {
    font-size: 16px;
    margin-bottom: 24px;
  }

.hero-image img{
    width:180px;
    max-width:100%;
    height:auto;
}

  .judge-btn {
    display: inline-block;
    width: 100%;
    padding: 14px;
    font-size: 16px;
  }

  /* Passport Banner */

  .passport-banner {
    padding: 16px;
  }

  .passport-banner span {
    font-size: 1.2rem;
  }

  .passport-banner p {
    font-size: 14px;
  }

  /* Welcome */

  .welcome-card {
    padding: 20px;
  }

  .welcome-card h2 {
    font-size: 26px;
  }

  .welcome-card p {
    font-size: 16px;
  }

  /* Rules */

  .rules-section {
    padding: 24px;
    display: block;
  }

  .rules-section h2 {
    font-size: 26px;
    margin-bottom: 24px;
  }

  .rule {
    margin-bottom: 30px;
  }

  .rule h3 {
    font-size: 18px;
  }

  .rule p {
    font-size: 15px;
  }

  .arrow {
    display: block;
    font-size: 36px;
  }

}
</style>