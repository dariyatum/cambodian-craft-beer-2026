<template>
  <div class="beer-page">
    <h1 class="beer-page__title">European brewery — beer styles</h1>

    <div class="beer-list">
      <BeerCard
        v-for="beer in beers"
        :key="beer.title"
        v-bind="beer"
      />
    </div>
  </div>
</template>

<script setup>
const beers = [
  { title: 'Strong Bitter (ESB)', country: 'England', abv: '4.6% – 6.2%', ibu: '30 - 50', description: 'An average- to strong-strength English ale featuring a nice balance between leafy, earthy British hops and a solid malt backbone. Expect notes of biscuit, nut, or caramel with a dry, clean finish.' },
  { title: 'English IPA', country: 'England', abv: '5.0% – 7.5%', ibu: '40 - 60', description: 'A hoppy, moderately strong British pale ale that leans into herbal, floral, and spicy wood qualities rather than the bright citrus of its American cousin. The malt profile is often more prominent here, presenting toasted, bready, or caramel layers.' },
  { title: 'Witbier', country: 'Belgium', abv: '4.5% – 5.5%', ibu: '8 - 20', description: 'A remarkably refreshing, pale wheat ale brewed with coriander and curaçao orange peel. It is intentionally hazy from unmalted wheat and yeast, offering a bright, citrusy, and subtly spicy flavor profile.' },
  { title: 'Saison', country: 'Belgium', abv: '3.5% – 9.5%', ibu: '20 - 35', description: 'An artisanal, highly carbonated Belgian farmhouse ale with a distinctive dry, fruity, and peppery character. It balances complex esters and phenols with a prominent hop bitterness and an incredibly crisp finish.' },
  { title: 'Weissbier', country: 'Germany', abv: '4.3% – 5.6%', ibu: '8 - 15', description: 'A traditional South German wheat beer famous for its cloudy appearance and dramatic yeast-driven aromas of banana and clove. It has low bitterness, high carbonation, and a fluffy, creamy mouthfeel.' },
  { title: 'German Pils', country: 'Germany', abv: '4.4% – 5.2%', ibu: '22 - 40', description: 'A crisp, clean, and highly attenuated gold-colored lager that highlights noble German hops like Hallertau or Tettnanger. It features a distinctive, snappy floral aroma and a firm, lingering bitterness.' },
  { title: 'Munich Dunkel', country: 'Germany', abv: '4.5% – 5.6%', ibu: '18 – 28', description: 'A classic, deeply comforting dark lager from Bavaria that celebrates rich, bready, and toasty Munich malts. It tastes of bread crusts, nuts, or mild chocolate without ever feeling heavy, overly sweet, or roasted like a stout.' },
]
</script>

<style scoped>
.beer-page {
  background: #F4E8D0;
  min-height: 100vh;
  padding: 40px 16px;
}
.beer-page__title {
  max-width: 700px;
  margin: 0 auto 24px;
  font-size: 26px;
  font-weight: 700;
  color: #2C1810;
  font-family: Georgia, serif;
}
.beer-list {
  display: flex;
  flex-direction: column;
  gap: 14px;
  max-width: 700px;
  margin: 0 auto;
}
</style>