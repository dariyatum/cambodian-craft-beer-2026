<template>
  <div class="beer-card">
    <div class="beer-card__header">
      <p class="beer-card__title">{{ title }}</p>
      <p class="beer-card__country">{{ country }}</p>
    </div>

    <div class="beer-card__stats">
      <div>
        <p class="stat-label">ABV</p>
        <p class="stat-value">{{ abv }}</p>
      </div>
      <div>
        <p class="stat-label">IBU</p>
        <p class="stat-value">{{ ibu }}</p>
      </div>
    </div>

    <p v-if="showDesc" class="beer-card__desc">{{ description }}</p>

    <button class="beer-card__toggle" @click="showDesc = !showDesc">
      {{ showDesc ? 'See less' : 'See more' }}
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  title: String,
  country: String,
  abv: String,
  ibu: String,
  description: String,
})

const showDesc = ref(false)
</script>

<style scoped>
.beer-card {
  background: #FFF9EF;
  border: 1px solid #e8dcc4;
  border-radius: 14px;
  padding: 20px 24px;
}
.beer-card__header {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 12px;
  margin-bottom: 14px;
}
.beer-card__title {
  font-size: 19px;
  font-weight: 700;
  margin: 0;
  color: #2C1810;
  font-family: Georgia, serif;
}
.beer-card__country {
  font-size: 11px;
  color: #C89A2B;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  font-weight: 700;
  white-space: nowrap;
  margin: 0;
}
.beer-card__stats {
  display: flex;
  gap: 28px;
  margin-bottom: 14px;
}
.stat-label {
  font-size: 11px;
  color: #a89878;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  margin: 0 0 3px;
}
.stat-value {
  font-size: 15px;
  font-weight: 700;
  margin: 0;
  color: #2C1810;
}
.beer-card__desc {
  font-size: 13px;
  color: #5a4e3c;
  line-height: 1.65;
  margin: 0 0 10px;
}
.beer-card__toggle {
  background: none;
  border: none;
  color: #7A2E24;
  font-size: 13px;
  font-weight: 700;
  padding: 0;
  cursor: pointer;
}
.beer-card__toggle:hover {
  text-decoration: underline;
}
</style>