<template>
  <div class="sponsor-section reveal">

    <div class="sponsor-section__header">
      <div class="sponsor-section__title-block">
        <span class="sponsor-section__tier-dot" :class="`dot--${tier}`"></span>
        <h2 class="sponsor-section__title">{{ title }}</h2>
      </div>
    </div>

    <div class="sponsor-grid">
      <SponsorCard
        v-for="(sponsor, i) in sponsors"
        :key="sponsor.name"
        :sponsor="sponsor"
        :tier="tier"
        :style="{ '--delay': `${i * 80}ms` }"
        class="reveal-card"
      />
    </div>

  </div>
</template>

<script setup>
import SponsorCard from './SponsorCard.vue'
import { onMounted } from 'vue'

defineProps({
  title:    { type: String, default: 'Sponsors' },
  sponsors: { type: Array,  required: true, default: () => [] },
  tier:     { type: String, default: 'partner' },
})

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.08 }
  )
  document.querySelectorAll('.reveal, .reveal-card').forEach(el => observer.observe(el))
})
</script>

<style scoped>
.sponsor-section {
  max-width: 1080px;
  margin: 0 auto;
  padding: 0 24px 52px;
}

.sponsor-section__header {
  margin-bottom: 20px;
  padding-bottom: 16px;
  border-bottom: 1px solid rgba(200, 155, 60, 0.2);
}

.sponsor-section__title-block {
  display: flex;
  align-items: center;
  gap: 10px;
}

.sponsor-section__tier-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}

.dot--platinum { background: #c89b3c; }
.dot--gold     { background: #d7a332; }
.dot--silver   { background: #8a9ba8; }
.dot--partner  { background: rgba(248, 231, 193, 0.5); }

.sponsor-section__title {
  font-size: 0.8125rem;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: rgba(248, 231, 193, 0.6);
}

.sponsor-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.reveal-card {
  opacity: 0;
  transform: translateY(16px);
  transition:
    opacity 0.4s ease var(--delay, 0ms),
    transform 0.4s ease var(--delay, 0ms);
}

.reveal-card.is-visible {
  opacity: 1;
  transform: translateY(0);
}

@media (prefers-reduced-motion: reduce) {
  .reveal,
  .reveal-card {
    opacity: 1;
    transform: none;
    transition: none;
  }
}

@media (max-width: 768px) {
  .sponsor-section {
    padding: 0 16px 40px;
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