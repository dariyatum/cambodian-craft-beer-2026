<template>
  <div class="sponsors-page">

    <div class="hero reveal">
      <p class="eyebrow">❦ Cambodia Craft Beer Crown 2026 ❦</p>
      <h1 class="hero__title">Our Sponsors</h1>
      <p class="hero__subtitle">
        We thank our generous sponsors who make the Cambodian Craft Beer Crown 2026 possible.
      </p>
    </div>

    <SponsorSection title="Platinum Sponsors" :sponsors="platinumSponsors" tier="platinum" />
    <SponsorSection title="Gold Sponsors"     :sponsors="goldSponsors"     tier="gold"     />
    <SponsorSection title="Silver Sponsors"   :sponsors="silverSponsors"   tier="silver"   />
    <SponsorSection title="Partners"          :sponsors="partnerSponsors"  tier="partner"  />

  </div>
</template>

<script setup>
import { onMounted } from 'vue'

const platinumSponsors = [
  { name: 'Bertie',                 logo: '/images/BERTIE.webp',                  description: 'Official event partner.' },
  { name: 'Botanico',               logo: '/images/botanico.webp',                description: 'Premium beer supplier.' },
  { name: 'Yakima Chief',           logo: '/images/YAKIMA CHIEF.webp',            description: 'Hop supplier.' },
]
const goldSponsors = [
  { name: 'Thai Tan',               logo: '/images/thai tan.webp',                description: 'Community supporter.' },
  { name: 'Skai Tech',              logo: '/images/SKAI_Tech.webp',               description: 'Technology partner.' },
  { name: 'Craft Beer Association', logo: '/images/CRAFT BEER ASSOCIATION.webp',  description: 'Industry partner.' },
]
const silverSponsors = [
  { name: 'Silver Sponsor 1',       logo: '/images/BERTIE.webp',                  description: 'Sponsor description.' },
  { name: 'Silver Sponsor 2',       logo: '/images/botanico.webp',                description: 'Sponsor description.' },
  { name: 'Silver Sponsor 3',       logo: '/images/YAKIMA CHIEF.webp',            description: 'Sponsor description.' },
]
const partnerSponsors = [
  { name: 'Partner 1',              logo: '/images/SKAI_Tech.webp',               description: 'Partner description.' },
  { name: 'Partner 2',              logo: '/images/thai tan.webp',                description: 'Partner description.' },
  { name: 'Partner 3',              logo: '/images/BERTIE.webp',                  description: 'Partner description.' },
]

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
    { threshold: 0.1 }
  )
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el))
})
</script>

<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.sponsors-page {
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
}

.hero {
  max-width: 1080px;
  margin: 0 auto;
  padding: 64px 24px 48px;
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

.hero__title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 900;
  color: #f8e7c1;
  text-transform: uppercase;
  letter-spacing: 4px;
  line-height: 1;
  margin-bottom: 14px;
}

.hero__subtitle {
  font-size: 1rem;
  color: rgba(248, 231, 193, 0.75);
  line-height: 1.65;
  max-width: 56ch;
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

@media (prefers-reduced-motion: reduce) {
  .reveal {
    opacity: 1;
    transform: none;
    transition: none;
  }
}

@media (max-width: 640px) {
  .hero {
    padding: 48px 16px 36px;
  }
}
</style>