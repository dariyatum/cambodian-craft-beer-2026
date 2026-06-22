<template>
  <div class="beer-card">
    <img :src="img" class="beer-card__img" />
    <div class="beer-card__body">
      <h3 class="beer-card__title">{{ title }}</h3>

      <p class="beer-card__label">Alcohol level (%)</p>
      <p class="beer-card__value">{{ abv }}</p>

      <p class="beer-card__label">Bitterness (IBU)</p>
      <p class="beer-card__value">{{ ibu }}</p>

      <p class="beer-card__desc">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  img: String,
  title: String,
  abv: String,
  ibu: String,
  description: String,
})
</script>

<style scoped>
.beer-card {
  display: flex;
  gap: 24px;
  background: #7a3328;
  border-radius: 16px;
  padding: 24px;
  box-shadow: 0 6px 14px rgba(0,0,0,0.25);
}
.beer-card__img {
  width: 140px;
  object-fit: contain;
}
.beer-card__title {
  color: #fff;
  font-family: Georgia, serif;
  font-weight: 800;
  font-size: 26px;
  margin: 0 0 8px;
}
.beer-card__label {
  color: #e0a82e;
  font-weight: 700;
  font-size: 13px;
  margin: 4px 0 0;
}
.beer-card__value {
  color: #f3d9a4;
  font-weight: 700;
  font-size: 15px;
  margin: 0 0 6px;
}
.beer-card__desc {
  background: #dba23f;
  color: #5c2a1e;
  font-weight: 700;
  font-size: 13px;
  line-height: 1.6;
  border-radius: 10px;
  padding: 14px 18px;
  margin-top: 10px;
}
</style>