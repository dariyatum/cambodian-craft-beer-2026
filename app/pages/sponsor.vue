<template>
  <section class="sponsor-section">
    <div class="container">
      <h1>Sponsors</h1>

      <p class="subtitle">
        We thank our generous sponsors who make the Cambodian Craft Beer Crown
        2025 possible.
      </p>

      <div class="sponsor-grid">
        <div
          class="sponsor-card"
          v-for="sponsor in sponsors"
          :key="sponsor.name"
        >
          <img :src="sponsor.logo" :alt="sponsor.name" />

          <h3>{{ sponsor.name }}</h3>

          <p>{{ sponsor.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const sponsors = [
  {
    name: "BERTIE",
    logo: "/images/BERTIE.webp",
    description: "Official event partner."
  },
  {
    name: "BOTANICO",
    logo: "/images/botanico.webp",
    description: "Premium beer supplier."
  },
  {
    name: "CRAFT BEER ASSOCIATION",
    logo: "/images/CRAFT BEER ASSOCIATION.webp",
    description: "Local food provider."
  },
  {
    name: "THAI TAN",
    logo: "/images/thai tan.webp",
    description: "Community supporter."
  },
  {
    name: "YAKIMA CHIEF",
    logo: "/images/YAKIMA CHIEF.webp",
    description: "Craft beer enthusiast group."
  },
  {
    name: "SKAI TECH",
    logo: "/images/SKAI_Tech.webp",
    description: "Event logistics partner."
  }
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
}
.sponsor-section {
  background: #f7f4ee;
  padding: 80px 20px;
}

.container {
  max-width: 1200px;
  margin: auto;
  text-align: center;
}

h1 {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 15px;
}

.subtitle {
  max-width: 700px;
  margin: 0 auto 60px;
  font-size: 18px;
  color: #333;
}

.sponsor-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 50px;
}

.sponsor-card {
  background: #e8dfcf;
  border-radius: 12px;
  padding: 30px 20px;
  transition: 0.3s ease;
}

.sponsor-card:hover {
  transform: translateY(-5px);
}

.sponsor-card img {
  width: 120px;
  height: 120px;
  object-fit: contain;
  margin-bottom: 20px;
}

.sponsor-card h3 {
  font-size: 16px;
  font-weight: 700;
  margin-bottom: 8px;
}

.sponsor-card p {
  font-size: 14px;
  color: #444;
}

@media (max-width: 768px) {
  .sponsor-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 576px) {
  .sponsor-grid {
    grid-template-columns: 1fr;
  }

  h1 {
    font-size: 36px;
  }
}
</style>