<template>
  <div class="beer-card">
    <div class="beer-card__header">
      <div class="beer-card__top">
        <span class="beer-card__flag">{{ countryFlag }}</span>
        <div class="beer-card__meta">
          <h3 class="beer-card__title">{{ title }}</h3>
          <div class="beer-card__row">
            <span class="badge">ABV {{ abv }}</span>
            <span class="badge badge--ibu">IBU {{ ibu }}</span>
          </div>
        </div>
      </div>
    </div>

    <div class="beer-card__body" :class="{ 'is-open': isOpen }">
      <div class="beer-card__body-inner">
        <p class="beer-card__description">{{ description }}</p>
      </div>
    </div>

    <button class="beer-card__toggle" @click="isOpen = !isOpen">
      {{ isOpen ? 'Hide' : 'Read more' }}
      <i class="fa-solid" :class="isOpen ? 'fa-chevron-up' : 'fa-chevron-down'"></i>
    </button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  title: String,
  country: String,
  abv: String,
  ibu: String,
  description: String,
})

const isOpen = ref(false)

const flagMap = {
  'England': '🏴󠁧󠁢󠁥󠁮󠁧󠁿',
  'Belgium': '🇧🇪',
  'Germany': '🇩🇪',
  'France':  '🇫🇷',
  'USA':     '🇺🇸',
  'Japan':   '🇯🇵',
  'Cambodia':'🇰🇭',
}

const countryFlag = computed(() => flagMap[props.country] ?? '🍺')
</script>

<style scoped>
.beer-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 22px 24px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.beer-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.16);
}

/* ── Header ── */
.beer-card__header {
  margin-bottom: 14px;
}

.beer-card__top {
  display: flex;
  align-items: center;
  gap: 14px;
}

.beer-card__flag {
  font-size: 2rem;
  line-height: 1;
  flex-shrink: 0;
}

.beer-card__meta {
  flex: 1;
  min-width: 0;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.beer-card__title {
  font-size: 1.0625rem;
  font-weight: 800;
  color: #2d1508;
  line-height: 1.2;
}

.beer-card__row {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-wrap: wrap;
}

/* ── Badges ── */
.badge {
  display: inline-block;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(215, 163, 50, 0.5);
  border-radius: 6px;
  padding: 3px 10px;
  font-size: 0.75rem;
  font-weight: 700;
  white-space: nowrap;
}

.badge--ibu {
  background: transparent;
  color: #7e2527;
  border-color: rgba(126, 37, 39, 0.4);
}

/* ── Collapsible body ── */
.beer-card__body {
  display: grid;
  grid-template-rows: 0fr;
  transition: grid-template-rows 0.3s ease;
}

.beer-card__body.is-open {
  grid-template-rows: 1fr;
}

.beer-card__body-inner {
  overflow: hidden;
}

.beer-card__description {
  font-size: 0.9375rem;
  color: #4a2e1a;
  line-height: 1.7;
  padding-top: 2px;
  padding-bottom: 16px;
}

/* ── Toggle ── */
.beer-card__toggle {
  display: flex;
  align-items: center;
  gap: 6px;
  background: none;
  border: none;
  padding: 0;
  font-size: 0.875rem;
  font-weight: 700;
  color: #7e2527;
  cursor: pointer;
  font-family: 'Inter', sans-serif;
  transition: color 0.2s ease;
}

.beer-card__toggle:hover {
  color: #5c1b1d;
}

.beer-card__toggle i {
  font-size: 0.7rem;
}

@media (max-width: 480px) {
  .beer-card {
    padding: 18px 16px;
  }
}
</style>