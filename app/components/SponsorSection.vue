<template>
  <div class="sponsor-page">

    <div class="sponsor-page__hero">
      <p class="eyebrow">❦ Cambodia Craft Beer Crown 2026 ❦</p>
      <h1 class="sponsor-page__title">{{ title }}</h1>
      <p class="sponsor-page__subtitle">{{ subtitle }}</p>
    </div>

    <div class="sponsor-grid">
      <SponsorCard
        v-for="sponsor in sponsors"
        :key="sponsor.name"
        :sponsor="sponsor"
      />
    </div>

  </div>
</template>

<script setup>
import SponsorCard from './SponsorCard.vue'

defineProps({
  title:    { type: String,  default: 'Sponsors' },
  subtitle: { type: String,  default: 'We thank our generous sponsors who make this event possible.' },
  sponsors: { type: Array,   required: true, default: () => [] },
})
</script>

<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}


.sponsor-section {
  background: #f7f4ee;
  padding: 30px 20px;

.sponsor-page {

  font-family: 'Inter', sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  padding: 64px 24px 80px;
  max-width: 1080px;
  margin: 0 auto;
}

.sponsor-page__hero {
  margin-bottom: 48px;
  text-align: left;
}

.eyebrow {
  font-size: 0.8125rem;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 12px;
}

.sponsor-page__title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 900;
  color: #f8e7c1;
  text-transform: uppercase;
  letter-spacing: 4px;
  line-height: 1;
  margin-bottom: 14px;
}

.sponsor-page__subtitle {
  font-size: 1rem;
  color: rgba(248, 231, 193, 0.75);
  line-height: 1.65;
  max-width: 56ch;
}

.sponsor-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

@media (max-width: 768px) {
  .sponsor-page {
    padding: 48px 16px 64px;
  }
  .sponsor-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .sponsor-grid {
    grid-template-columns: 1fr;
  }
}
</style>