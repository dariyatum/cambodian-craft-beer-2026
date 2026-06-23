<template>
  <div class="beer-page">

    <div class="beer-page__hero reveal">
      <p class="beer-page__eyebrow">❦ European Brewery ❦</p>
      <h1 class="beer-page__title">Beer Styles</h1>
      <p class="beer-page__subtitle">A guide to classic ales and lagers across England, Belgium, and Germany</p>
    </div>

    <div class="beer-page__filters reveal" style="--delay: 150ms">
      <select v-model="selectedCountry" class="filter-input">
        <option value="">All countries</option>
        <option v-for="c in countries" :key="c" :value="c">{{ c }}</option>
      </select>
    </div>

    <div class="beer-list">
      <BeerCard
        v-for="(beer, i) in filteredBeers"
        :key="beer.title"
        v-bind="beer"
        class="reveal-card"
        :style="{ '--delay': `${i * 80}ms` }"
      />
      <p v-if="filteredBeers.length === 0" class="no-results">
        No beer styles match your filter.
      </p>
    </div>

  </div>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue'

const beers = [
  {
    title: 'Strong Bitter (ESB)',
    country: 'England',
    abv: '4.6% – 6.2%',
    ibu: '30 – 50',
    description: 'An average- to strong-strength English ale featuring a nice balance between leafy, earthy British hops and a solid malt backbone. Expect notes of biscuit, nut, or caramel with a dry, clean finish.'
  },
  {
    title: 'English IPA',
    country: 'England',
    abv: '5.0% – 7.5%',
    ibu: '40 – 60',
    description: 'A hoppy, moderately strong British pale ale that leans into herbal, floral, and spicy wood qualities rather than the bright citrus of its American cousin. The malt profile is often more prominent here, presenting toasted, bready, or caramel layers.'
  },
  {
    title: 'Witbier',
    country: 'Belgium',
    abv: '4.5% – 5.5%',
    ibu: '8 – 20',
    description: 'A remarkably refreshing, pale wheat ale brewed with coriander and curaçao orange peel. It is intentionally hazy from unmalted wheat and yeast, offering a bright, citrusy, and subtly spicy flavor profile.'
  },
  {
    title: 'Saison',
    country: 'Belgium',
    abv: '3.5% – 9.5%',
    ibu: '20 – 35',
    description: 'An artisanal, highly carbonated Belgian farmhouse ale with a distinctive dry, fruity, and peppery character. It balances complex esters and phenols with a prominent hop bitterness and an incredibly crisp finish.'
  },
  {
    title: 'Weissbier',
    country: 'Germany',
    abv: '4.3% – 5.6%',
    ibu: '8 – 15',
    description: 'A traditional South German wheat beer famous for its cloudy appearance and dramatic yeast-driven aromas of banana and clove. It has low bitterness, high carbonation, and a fluffy, creamy mouthfeel.'
  },
  {
    title: 'German Pils',
    country: 'Germany',
    abv: '4.4% – 5.2%',
    ibu: '22 – 40',
    description: 'A crisp, clean, and highly attenuated gold-colored lager that highlights noble German hops like Hallertau or Tettnanger. It features a distinctive, snappy floral aroma and a firm, lingering bitterness.'
  },
  {
    title: 'Munich Dunkel',
    country: 'Germany',
    abv: '4.5% – 5.6%',
    ibu: '18 – 28',
    description: 'A classic, deeply comforting dark lager from Bavaria that celebrates rich, bready, and toasty Munich malts. It tastes of bread crusts, nuts, or mild chocolate without ever feeling heavy, overly sweet, or roasted like a stout.'
  },
]

const selectedCountry = ref('')
const countries = computed(() => [...new Set(beers.map(b => b.country))])
const filteredBeers = computed(() =>
  beers.filter(b => !selectedCountry.value || b.country === selectedCountry.value)
)

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
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.beer-page {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  min-height: 100vh;
  padding: 64px 24px 80px;
}

.beer-page__hero {
  max-width: 680px;
  margin: 0 auto 40px;
  text-align: left;
}

.beer-page__eyebrow {
  font-size: 0.8125rem;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 12px;
}

.beer-page__title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 900;
  color: #f8e7c1;
  text-transform: uppercase;
  letter-spacing: 4px;
  line-height: 1;
  margin-bottom: 14px;
}

.beer-page__subtitle {
  font-size: 1rem;
  color: rgba(248, 231, 193, 0.75);
  line-height: 1.65;
}

.beer-page__filters {
  max-width: 680px;
  margin: 0 auto 28px;
}

.filter-input {
  width: 100%;
  max-width: 260px;
  padding: 10px 14px;
  border-radius: 8px;
  border: 1px solid rgba(200, 155, 60, 0.5);
  background: #fdf6e8;
  color: #2d1508;
  font-size: 0.9375rem;
  font-family: 'Inter', sans-serif;
  cursor: pointer;
}

.filter-input:focus {
  outline: none;
  border-color: #c89b3c;
}

.beer-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  max-width: 680px;
  margin: 0 auto;
}

.no-results {
  text-align: center;
  color: rgba(248, 231, 193, 0.75);
  font-size: 0.9375rem;
  margin-top: 32px;
}

.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition:
    opacity 0.5s ease var(--delay, 0ms),
    transform 0.5s ease var(--delay, 0ms);
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

@media (max-width: 640px) {
  .beer-page {
    padding: 48px 16px 64px;
  }
  .filter-input {
    max-width: 100%;
  }
}
</style>