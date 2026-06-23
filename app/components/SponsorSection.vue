<template>
  <section class="sponsor-section">
    <div class="container">
      <h1>{{ title }}</h1>

      <p class="subtitle">{{ subtitle }}</p>

      <div class="sponsor-grid">
        <SponsorCard
          v-for="sponsor in sponsors"
          :key="sponsor.name"
          :sponsor="sponsor"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import SponsorCard from './SponsorCard.vue'

defineProps({
  title: {
    type: String,
    default: 'Sponsors'
  },
  subtitle: {
    type: String,
    default: 'We thank our generous sponsors who make this event possible.'
  },
  sponsors: {
    type: Array,
    required: true,
    default: () => []
  }
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

.sponsor-section {
  background: #f7f4ee;
  padding: 30px 20px;
  font-family: 'Inter', sans-serif;
}

.container {
  max-width: 1200px;
  margin: auto;
  text-align: center;
}

h1 {
  font-size: 40px;
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
