<template>
  <div class="beer-page">
    <div class="beer-page__bg"></div>
    <div class="beer-page__content">
      <div class="beer-page__hero">
        <p class="beer-page__eyebrow">European brewery</p>
        <h1 class="beer-page__title">Beer styles</h1>
        <p class="beer-page__subtitle">A guide to classic ales and lagers across England, Belgium, and Germany</p>
      </div>

      <div class="beer-page__filters">
        <select v-model="selectedCountry" class="filter-input">
          <option value="">All countries</option>
          <option v-for="c in countries" :key="c" :value="c">{{ c }}</option>
        </select>
      </div>

      <div class="beer-list">
        <BeerCard
          v-for="beer in filteredBeers"
          :key="beer.title"
          v-bind="beer"
        />

        <p v-if="filteredBeers.length === 0" class="no-results">
          No beer styles match your search.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const beers = [
  { title: 'Strong Bitter (ESB)', country: 'England', abv: '4.6% – 6.2%', ibu: '30 - 50', description: 'An average- to strong-strength English ale featuring a nice balance between leafy, earthy British hops and a solid malt backbone. Expect notes of biscuit, nut, or caramel with a dry, clean finish.' },
  { title: 'English IPA', country: 'England', abv: '5.0% – 7.5%', ibu: '40 - 60', description: 'A hoppy, moderately strong British pale ale that leans into herbal, floral, and spicy wood qualities rather than the bright citrus of its American cousin. The malt profile is often more prominent here, presenting toasted, bready, or caramel layers.' },
  { title: 'Witbier', country: 'Belgium', abv: '4.5% – 5.5%', ibu: '8 - 20', description: 'A remarkably refreshing, pale wheat ale brewed with coriander and curaçao orange peel. It is intentionally hazy from unmalted wheat and yeast, offering a bright, citrusy, and subtly spicy flavor profile.' },
  { title: 'Saison', country: 'Belgium', abv: '3.5% – 9.5%', ibu: '20 - 35', description: 'An artisanal, highly carbonated Belgian farmhouse ale with a distinctive dry, fruity, and peppery character. It balances complex esters and phenols with a prominent hop bitterness and an incredibly crisp finish.' },
  { title: 'Weissbier', country: 'Germany', abv: '4.3% – 5.6%', ibu: '8 - 15', description: 'A traditional South German wheat beer famous for its cloudy appearance and dramatic yeast-driven aromas of banana and clove. It has low bitterness, high carbonation, and a fluffy, creamy mouthfeel.' },
  { title: 'German Pils', country: 'Germany', abv: '4.4% – 5.2%', ibu: '22 - 40', description: 'A crisp, clean, and highly attenuated gold-colored lager that highlights noble German hops like Hallertau or Tettnanger. It features a distinctive, snappy floral aroma and a firm, lingering bitterness.' },
  { title: 'Munich Dunkel', country: 'Germany', abv: '4.5% – 5.6%', ibu: '18 – 28', description: 'A classic, deeply comforting dark lager from Bavaria that celebrates rich, bready, and toasty Munich malts. It tastes of bread crusts, nuts, or mild chocolate without ever feeling heavy, overly sweet, or roasted like a stout.' },
]

const search = ref('')
const selectedCountry = ref('')

const countries = computed(() => [...new Set(beers.map(b => b.country))])

const filteredBeers = computed(() => {
  return beers.filter(beer => {
    const matchesSearch = beer.title.toLowerCase().includes(search.value.toLowerCase())
    const matchesCountry = !selectedCountry.value || beer.country === selectedCountry.value
    return matchesSearch && matchesCountry
  })
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Fraunces:opsz,wght@9..144,500;9..144,700&display=swap');

.beer-page {
  position: relative;
  font-family: 'Inter', sans-serif;
  min-height: 100vh;
  width: 100%;
  padding: 72px 16px 48px;
  overflow-x: hidden;
  box-sizing: border-box;
}

.beer-page__bg {
  position: absolute;
  inset: 0;
  background:
    linear-gradient(180deg, rgba(15, 8, 6, 0.88) 0%, rgba(35, 16, 12, 0.78) 45%, rgba(15, 8, 6, 0.92) 100%),
    url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b');
  background-size: cover;
  background-position: center;
  z-index: 0;
}

.beer-page__content {
  position: relative;
  z-index: 1;
}

.beer-page__hero {
  max-width: 700px;
  margin: 0 auto 36px;
  text-align: center;
}
.beer-page__eyebrow {
  display: inline-block;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: #E8B23D;
  margin: 0 0 14px;
  padding: 5px 14px;
  border: 1px solid rgba(232, 178, 61, 0.4);
  border-radius: 100px;
  background: rgba(232, 178, 61, 0.08);
}
.beer-page__title {
  font-family: 'Fraunces', Georgia, serif;
  font-size: 44px;
  font-weight: 700;
  color: #FFF7EA;
  margin: 0 0 10px;
  letter-spacing: -0.01em;
  text-shadow: 0 2px 24px rgba(0, 0, 0, 0.4);
}
.beer-page__subtitle {
  font-size: 14.5px;
  color: rgba(240, 227, 207, 0.75);
  margin: 0;
  line-height: 1.5;
  padding: 0 8px;
}

.beer-page__filters {
  display: flex;
  gap: 12px;
  max-width: 700px;
  margin: 0 auto 28px;
}
.filter-input {
  flex: 1;
  padding: 13px 16px;
  border-radius: 12px;
  border: 1px solid rgba(255, 247, 234, 0.18);
  background: rgba(30, 18, 13, 0.55);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  color: #FFF7EA;
  font-size: 14px;
  font-weight: 500;
  appearance: none;
  cursor: pointer;
  transition: border-color 0.2s ease, background 0.2s ease;
}
.filter-input:hover {
  border-color: rgba(232, 178, 61, 0.45);
}
.filter-input:focus {
  outline: none;
  border-color: #E8B23D;
  background: rgba(30, 18, 13, 0.75);
}
.filter-input option {
  background: #241510;
  color: #FFF7EA;
}

.beer-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  max-width: 700px;
  margin: 0 auto;
}

.no-results {
  text-align: center;
  color: rgba(240, 227, 207, 0.65);
  margin-top: 24px;
  font-size: 14px;
}

/* ---- Tablet ---- */
@media (max-width: 600px) {
  .beer-page {
    padding: 56px 14px 40px;
  }
  .beer-page__title {
    font-size: 34px;
  }
  .beer-page__subtitle {
    font-size: 13.5px;
  }
}

@media (max-width: 480px) {
  .beer-page {
    padding: 40px 12px 32px;
  }
  .beer-page__hero {
    margin: 0 auto 24px;
  }
  .beer-page__eyebrow {
    font-size: 10px;
    padding: 4px 12px;
    margin: 0 0 10px;
  }
  .beer-page__title {
    font-size: 28px;
  }
  .beer-page__subtitle {
    font-size: 13px;
    padding: 0 4px;
  }
  .beer-page__filters {
    margin: 0 auto 20px;
  }
  .filter-input {
    padding: 12px 14px;
    font-size: 13.5px;
  }
  .beer-list {
    gap: 12px;
  }
}
</style>