<template>
  <div class="sponsor-card">
    <div class="sponsor-card__logo">
      <img :src="sponsor.logo" :alt="sponsor.name" loading="lazy" />
    </div>
    <h3 class="sponsor-card__name">{{ sponsor.name }}</h3>
    <p class="sponsor-card__description">{{ sponsor.description }}</p>
  </div>
</template>

<script setup>
defineProps({
  sponsor: {
    type: Object,
    required: true,
  }
})
</script>

<style scoped>
.sponsor-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 32px 24px 28px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.sponsor-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.14);
}

.sponsor-card__logo {
  width: 96px;
  height: 96px;
  background: #fffaf0;
  border-radius: 50%;
  border: 2px solid rgba(200, 155, 60, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  flex-shrink: 0;
}

.sponsor-card__logo img {
  width: 68px;
  height: 68px;
  object-fit: contain;
}

.sponsor-card__name {
  font-size: 0.9375rem;
  font-weight: 800;
  color: #2d1508;
  letter-spacing: 0.5px;
  margin-bottom: 8px;
}

.sponsor-card__description {
  font-size: 0.875rem;
  color: #4a2e1a;
  line-height: 1.6;
}
</style>