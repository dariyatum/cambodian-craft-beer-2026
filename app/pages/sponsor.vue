<template>
  <div class="sponsors-page">
    <!-- Main Title -->
    <div class="hero">
      <h1>OUR SPONSORS</h1>
      <p>
        We thank our generous sponsors who make the Cambodian Craft Beer Crown
        2025 possible.
      </p>
    </div>

    <SponsorSection
      title="Platinum Sponsors"
      :sponsors="platinumSponsors"
    />

    <SponsorSection
      title="Gold Sponsors"
      :sponsors="goldSponsors"
    />

    <SponsorSection
      title="Silver Sponsors"
      :sponsors="silverSponsors"
    />

    <SponsorSection
      title="Partners Sponsors"
      :sponsors="partnerSponsors"
    />
  </div>
</template>

<script setup>
import SponsorSection from '@/components/SponsorSection.vue'

const platinumSponsors = [
  {
    name: 'BERTIE',
    logo: '/images/BERTIE.webp',
    description: 'Official event partner.'
  },
  {
    name: 'BOTANICO',
    logo: '/images/botanico.webp',
    description: 'Premium beer supplier.'
  },
  {
    name: 'YAKIMA CHIEF',
    logo: '/images/YAKIMA CHIEF.webp',
    description: 'Hop supplier.'
  }
]

const goldSponsors = [
  {
    name: 'THAI TAN',
    logo: '/images/thai tan.webp',
    description: 'Community supporter.'
  },
  {
    name: 'SKAI TECH',
    logo: '/images/SKAI_Tech.webp',
    description: 'Technology partner.'
  },
  {
    name: 'CRAFT BEER ASSOCIATION',
    logo: '/images/CRAFT BEER ASSOCIATION.webp',
    description: 'Industry partner.'
  }
]

const silverSponsors = [
  {
    name: 'Silver Sponsor 1',
    logo: '/images/BERTIE.webp',
    description: 'Sponsor description.'
  },
  {
    name: 'Silver Sponsor 2',
    logo: '/images/botanico.webp',
    description: 'Sponsor description.'
  },
  {
    name: 'Silver Sponsor 3',
    logo: '/images/YAKIMA CHIEF.webp',
    description: 'Sponsor description.'
  }
]

const partnerSponsors = [
  {
    name: 'Partner 1',
    logo: '/images/SKAI_Tech.webp',
    description: 'Partner description.'
  },
  {
    name: 'Partner 2',
    logo: '/images/thai tan.webp',
    description: 'Partner description.'
  },
  {
    name: 'Partner 3',
    logo: '/images/BERTIE.webp',
    description: 'Partner description.'
  }
]
</script>

<style scoped>
.sponsors-page {
  background: #f7f4ee;
}

.hero {
  text-align: center;
  padding: 30px 20px 40px;
}

.hero h1 {
  font-size: 50px;
  font-weight: 800;
  margin-bottom: 10px;
}

.hero p {
  max-width: 700px;
  margin: 0 auto;
  font-size: 18px;
  color: #555;
}
</style>