<template>
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">


<section class="hero">

  <div class="image">
    <img src="/images/bg-schedule.jpg" alt="">
  </div>

  <div class="content">

    <span class="title">Even Schedule</span>
    <h2></h2>
    <p></p>

  </div>

</section>
</template>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

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

    min-height: 100vh;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  
}



.hero {
  display: flex;
  align-items: center;
  gap: 60px;
  max-width: 1200px;
  margin: auto 100px;
  padding: 0 20px;
}


.image{
  flex: 1;
}

.image img{
  width: 100%;
  display: block;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}

.content {
  flex: 1;
}

.title {
  color: chocolate;
  font-weight: 600;
  letter-spacing: 2px;
}

. h2 {
  color: #000;
  line-height: 1.8;

}


.content p{
  color: #000;
  line-height: 1.8;
  margin-bottom: 30px;
}

</style>