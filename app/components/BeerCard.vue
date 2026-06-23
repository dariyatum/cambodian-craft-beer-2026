<template>
  <div class="beer-card">
    <div class="beer-card__header">
      <div class="beer-card__meta">
        <p class="beer-card__country">{{ country }}</p>
        <h3 class="beer-card__title">{{ title }}</h3>
      </div>
      <div class="beer-card__badges">
        <span class="badge">ABV {{ abv }}</span>
        <span class="badge badge--ibu">IBU {{ ibu }}</span>
      </div>
    </div>
    <p class="beer-card__description">{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  country: String,
  abv: String,
  ibu: String,
  description: String,
})
</script>

<style scoped>
.beer-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 24px 28px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.beer-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.16);
}

.beer-card__header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 14px;
}

.beer-card__meta {
  flex: 1;
  min-width: 0;
}

.beer-card__country {
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 4px;
}

.beer-card__title {
  font-size: 1.125rem;
  font-weight: 800;
  color: #2d1508;
  line-height: 1.2;
}

.beer-card__badges {
  display: flex;
  flex-direction: column;
  gap: 6px;
  flex-shrink: 0;
}

.badge {
  display: inline-block;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(215, 163, 50, 0.5);
  border-radius: 6px;
  padding: 4px 10px;
  font-size: 0.75rem;
  font-weight: 700;
  white-space: nowrap;
  text-align: center;
}

.badge--ibu {
  background: transparent;
  color: #7e2527;
  border-color: rgba(126, 37, 39, 0.4);
}

.beer-card__description {
  font-size: 0.9375rem;
  color: #4a2e1a;
  line-height: 1.7;
}

@media (max-width: 480px) {
  .beer-card {
    padding: 20px;
  }
  .beer-card__header {
    flex-direction: column;
    gap: 10px;
  }
  .beer-card__badges {
    flex-direction: row;
  }
}
</style>