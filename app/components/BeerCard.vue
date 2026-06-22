<template>
  <div class="beer-card">
    <div class="beer-card__accent"></div>
    <div class="beer-card__body">
      <div class="beer-card__header">
        <p class="beer-card__title">{{ title }}</p>
        <p class="beer-card__country">{{ country }}</p>
      </div>
      <div class="beer-card__stats">
        <div class="stat">
          <p class="stat-label">ABV</p>
          <p class="stat-value">{{ abv }}</p>
        </div>
        <div class="stat-divider"></div>
        <div class="stat">
          <p class="stat-label">IBU</p>
          <p class="stat-value">{{ ibu }}</p>
        </div>
      </div>
      <transition name="desc">
        <p v-if="showDesc" class="beer-card__desc">{{ description }}</p>
      </transition>
      <button class="beer-card__toggle" @click="showDesc = !showDesc">
        {{ showDesc ? 'See less' : 'See more' }}
        <span class="beer-card__toggle-icon" :class="{ 'is-open': showDesc }">⌄</span>
      </button>
    </div>
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
  position: relative;
  display: flex;
  background: #FFF9EF;
  border: 1px solid rgba(200, 154, 43, 0.25);
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 4px 16px rgba(44, 24, 16, 0.08);
  transition: transform 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
}
.beer-card:hover {
  transform: translateY(-2px);
  border-color: rgba(200, 154, 43, 0.5);
  box-shadow: 0 10px 24px rgba(44, 24, 16, 0.14);
}

.beer-card__accent {
  width: 4px;
  flex-shrink: 0;
  background: linear-gradient(180deg, #C89A2B, #7A2E24);
}

.beer-card__body {
  flex: 1;
  padding: 22px 26px;
  min-width: 0;
}

.beer-card__header {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 12px;
  margin-bottom: 16px;
  flex-wrap: wrap;
}
.beer-card__title {
  font-family: 'Fraunces', Georgia, serif;
  font-size: 20px;
  font-weight: 700;
  margin: 0;
  color: #2C1810;
  letter-spacing: -0.01em;
}
.beer-card__country {
  font-size: 10.5px;
  color: #7A2E24;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-weight: 700;
  white-space: nowrap;
  margin: 0;
  padding: 4px 10px;
  border-radius: 100px;
  background: #F4E8D0;
}

.beer-card__stats {
  display: flex;
  align-items: center;
  gap: 24px;
  margin-bottom: 16px;
}
.stat-divider {
  width: 1px;
  height: 26px;
  background: rgba(44, 24, 16, 0.12);
}
.stat-label {
  font-size: 10.5px;
  color: #a89878;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin: 0 0 3px;
}
.stat-value {
  font-size: 15px;
  font-weight: 700;
  margin: 0;
  color: #2C1810;
}

.beer-card__desc {
  font-size: 13.5px;
  color: #5a4e3c;
  line-height: 1.7;
  margin: 0 0 14px;
}
.desc-enter-active, .desc-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}
.desc-enter-from, .desc-leave-to {
  opacity: 0;
  transform: translateY(-4px);
}

.beer-card__toggle {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  background: none;
  border: none;
  color: #7A2E24;
  font-size: 13px;
  font-weight: 600;
  padding: 6px 0;
  cursor: pointer;
  transition: color 0.15s ease;
  -webkit-tap-highlight-color: transparent;
}
.beer-card__toggle:hover {
  color: #C89A2B;
}
.beer-card__toggle-icon {
  display: inline-block;
  font-size: 14px;
  transition: transform 0.2s ease;
}
.beer-card__toggle-icon.is-open {
  transform: rotate(180deg);
}

/* ---- Tablet ---- */
@media (max-width: 600px) {
  .beer-card__body {
    padding: 18px 18px;
  }
}

/* ---- Phone ---- */
@media (max-width: 420px) {
  .beer-card__body {
    padding: 16px 16px;
  }
  .beer-card__header {
    margin-bottom: 12px;
  }
  .beer-card__title {
    font-size: 17px;
  }
  .beer-card__country {
    font-size: 9.5px;
    padding: 3px 8px;
  }
  .beer-card__stats {
    gap: 18px;
    margin-bottom: 12px;
  }
  .stat-value {
    font-size: 14px;
  }
  .beer-card__desc {
    font-size: 13px;
  }
}
</style>