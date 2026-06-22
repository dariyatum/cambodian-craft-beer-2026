<template>
  <div class="beer-page">
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
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

.beer-page {
  font-family: 'Inter', sans-serif;
  background:
    linear-gradient(rgba(44, 24, 16, 0.82), rgba(122, 46, 36, 0.55)),
    url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  min-height: 100vh;
  padding: 60px 16px 40px;
}

.beer-page__hero {
  max-width: 700px;
  margin: 0 auto 32px;
  text-align: center;
}
.beer-page__eyebrow {
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #C89A2B;
  margin: 0 0 8px;
}
.beer-page__title {
  font-family: Georgia, serif;
  font-size: 36px;
  font-weight: 700;
  color: #FFF9EF;
  margin: 0 0 8px;
}
.beer-page__subtitle {
  font-size: 14px;
  color: #f0e3cf;
  margin: 0;
}

.beer-page__filters {
  display: flex;
  gap: 12px;
  max-width: 700px;
  margin: 0 auto 24px;
}
.filter-input {
  flex: 1;
  padding: 10px 14px;
  border-radius: 10px;
  border: 1px solid rgba(255, 249, 239, 0.3);
  background: rgba(255, 249, 239, 0.95);
  color: #2C1810;
  font-size: 14px;
}
.filter-input:focus {
  outline: none;
  border-color: #C89A2B;
}

.beer-list {
  display: flex;
  flex-direction: column;
  gap: 14px;
  max-width: 700px;
  margin: 0 auto;
}

.no-results {
  text-align: center;
  color: #f0e3cf;
  margin-top: 24px;
}
</style> 