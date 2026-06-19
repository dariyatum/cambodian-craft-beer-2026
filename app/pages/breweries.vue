```vue
<template>
  <div class="container">
    <h1 class="title">Meet The Brewers</h1>
    <div class="divider">❦ ❦ ❦</div>

    <div class="brewery-grid">
      <div
        v-for="(brewery, index) in breweries"
        :key="brewery.name"
        class="brewery-card"
        data-aos="zoom-in"
        :data-aos-delay="index * 100"
      >
        <div class="logo">
          <img :src="brewery.logo" :alt="brewery.name" />
        </div>

        <h3>{{ brewery.name }}</h3>

        <p>{{ brewery.description }}</p>

        <a
          v-if="brewery.facebook !== 'NA'"
          :href="brewery.facebook"
          target="_blank"
          class="btn"
        >
          Meet Brewer
        </a>

        <span
          v-else
          class="btn disabled"
        >
          Coming Soon
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'

const breweries = ref([
  {
    name: "Sak Pub",
    logo: "sakpub.webp",
    description:
      "SAK PUB Craft Beer & Bites opened its taproom and kitchen in October 2021, serving handcrafted small-batch craft beer.",
    facebook: "https://www.facebook.com/SakPubCraftBeerBites"
  },
  {
    name: "Project Brews",
    logo: "images/projectbrews.png",
    description:
      "Projekt Brews is a small microbrewery based in Kampot since 2020 making modern hoppy beers.",
    facebook: "https://www.facebook.com/profile.php?id=100063463360069"
  },
  {
    name: "Botanico Brewing Company",
    logo: "images/blackbamboo.png",
    description:
      "One of Cambodia's oldest craft breweries creating a wide range of beers using local ingredients.",
    facebook: "https://www.facebook.com/botanicobrewingco"
  },
  {
    name: "Riel Brewing",
    logo: "images/riel.png",
    description:
      "A pioneering Phnom Penh brewery known for creative beers and Cambodian ingredients.",
    facebook: "https://www.facebook.com/rielbrewing"
  },
  {
    name: "Fuzzy Logic",
    logo: "images/fuzzylogic.png",
    description:
      "One of Cambodia's pioneering craft breweries known for consistent, balanced beers.",
    facebook: "https://www.facebook.com/FuzzyLogicCambodia"
  },
  {
    name: "Chug Lab",
    logo: "images/chuglab.png",
    description:
      "A nano brewery in Phnom Penh focused on high-quality modern craft beers.",
    facebook: "https://www.facebook.com/thechuglab"
  },
  {
    name: "Brew Khnear",
    logo: "images/brewkhnear.png",
    description:
      "Focused on bringing people together through quality craft beer.",
    facebook: "NA"
  },
  {
    name: "Funghi Art",
    logo: "images/funghiart.png",
    description: "Create new value for Cambodian rice through fermentation technology.We produce 3 kinds of beer, craft sake, sweet potato and rice Shochu and Gin. All made from Cambodian Rice.",
    facebook:"https://www.facebook.com/profile.php?id=100069892638809"
},
{
    name: "Jaya-Vara Meadery",
    logo: "images/jayavara.png",
    description: "Jaya-Vara Meadery has been crafting unique meads and beers in Cambodia for the past 3 years. started as a passion for traditional honey wine has evolved into a full-fledged brewery experimenting with bold flavors and local ingredients.",
    facebook:"https://www.facebook.com/profile.php?id=100080223013722"
},
{
    name: "Krama Craft Brewery",
    logo: "images/krama.png",
    description: "Krama Craft Brewery is a cozy craft brewery located in Siem Reap, founded by two partners — one French, one Cambodian. Just minutes from the city center, it offers creative, locally inspired beers like the Triple Khmer and Black IPA. With a warm atmosphere, Cambodian ingredients, and genuine hospitality, Krama is the perfect stop for a unique and authentic craft beer experience in Siem Reap",
    facebook:"https://www.facebook.com/profile.php?id=100095224728868",
},
{
    name: "Himawari Microbrewery",
    logo: "images/krama.png",
    description: "Himawari Microbrewery is the 1st and only microbrewery launched by it’s 5-star hotel-apartments in Cambodia. Made from the finest malt and hops, the beers crafted here are unique in flavour and of the highest quality. Himawari Microbrewery's brewmaster, Neo, has had many years of brewing experience and has designed 7 exclusive brews, 3 of which have won international awards. There’s definitely a craft beer for every palate.",
    facebook:"https://www.facebook.com/HimawariHotelMicrobrewery"
},
{
    name: "Bash Brewing",
    logo: "images/krama.png",
    description: "Bash Brewing is one of the Kingdom’s original craft breweries, creating some of the finest all-natural craft beer in Cambodia.",
    facebook:"https://www.facebook.com/bashbrewingkh"
},
])

onMounted(() => {
  AOS.init({
    duration: 1000,
    easing: 'ease-in-out',
    once: true
  })
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
}

.container {
  max-width: 1200px;
  margin: auto;
  padding: 60px 20px;
}

.title {
  color: #f8e7c1;
  font-size: 3.2rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 4px;
}

.divider {
  color: #c89b3c;
  font-size: 1.8rem;
  margin-bottom: 40px;
}

.brewery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}

.brewery-card {
  background: linear-gradient(180deg, #f8f0dc 0%, #efe2c0 100%);
  border: 3px solid #c89b3c;
  border-radius: 18px;
  padding: 25px;
  display: flex;
  flex-direction: column;
  transition: 0.3s ease;
}

.brewery-card:hover {
  transform: translateY(-8px);
}

.logo {
  height: 130px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.logo img {
  width: 100px;
  height: 100px;
  object-fit: contain;
  border-radius: 50%;
}

.btn {
  background: #7e2527;
  color: white;
  border-radius: 10px;
  padding: 12px 20px;
  text-decoration: none;
  text-align: center;
  margin-top: auto;
}

.disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

@media (max-width: 768px) {
  .title {
    font-size: 2rem;
  }

  .brewery-grid {
    grid-template-columns: 1fr;
  }
}
</style>


<style>
    *{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Inter',sans-serif;
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

.container{
    max-width:1200px;
    margin:auto;
    padding:60px 20px;
}

.title{
    color:#f8e7c1;
    font-size:3.2rem;
    font-weight:800;
    text-transform:uppercase;
    letter-spacing:4px;

    text-shadow:
        0 2px 8px rgba(0,0,0,.5),
        0 6px 20px rgba(0,0,0,.4);
}
.subtitle{
    text-align:center;
    color:#a37558;
    margin-bottom:40px;
}

.brewery-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:24px;
}

.brewery-card{
    background:
        linear-gradient(
            180deg,
            #f8f0dc 0%,
            #efe2c0 100%
        );

    border: 3px solid #c89b3c;
    border-radius: 18px;

    padding: 25px;

    display: flex;
    flex-direction: column;

    box-shadow:
        0 8px 20px rgba(0,0,0,.25),
        inset 0 0 15px rgba(255,255,255,.5);

    position: relative;

    transition: .3s ease;
}

.brewery-card:hover{
    transform: translateY(-8px);
    box-shadow:
        0 12px 30px rgba(0,0,0,.3),
        inset 0 0 15px rgba(255,255,255,.5);
}

.logo{
    height:130px;
    display:flex;
    justify-content:center;
    align-items:center;
    margin-bottom:20px;
}

.logo img{
    width:100px;
    height:100px;

    object-fit:contain;

    background:#fffaf0;

    border-radius:50%;

    border:4px solid #c89b3c;

    padding:10px;

    box-shadow:
        0 4px 12px rgba(0,0,0,.15);
}
.brewery-card h3{
    font-size:1.3rem;
    margin-bottom:12px;
    color:#2d1a10;
}

.brewery-card p{
    color:#362d26;
    line-height:1.6;
    flex-grow:1;
    margin-bottom:20px;
}

.btn{
    background:#7e2527;

    color:white;

    border:2px solid #d7a332;

    border-radius:10px;

    padding:12px 20px;

    font-weight:600;

    text-decoration:none;

    text-align:center;

    transition:.3s;
}

.btn:hover{
    background:#5f1b1d;
    transform:translateY(-2px);
}
.divider{
    text-align:left;
    color:#C89B3C;
    font-size:1.8rem;
    margin-bottom:40px;
}

@media(max-width:768px){

    .title{
        font-size:2rem;
    }

    .brewery-grid{
        grid-template-columns:1fr;
    }

}
</style>

<!-- in vue
<div class="brewery-grid">
    <div
        class="card"
        v-for="brewery in breweries"
        :key="brewery.name"
    >
        <img :src="brewery.logo">
        <h3>{{ brewery.name }}</h3>
        <p>{{ brewery.description }}</p>
    </div>
</div> -->  fix this with vue
