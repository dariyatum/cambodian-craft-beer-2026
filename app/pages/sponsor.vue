<template>
  <SponsorSection
    title="Sponsors"
    subtitle="We thank our generous sponsors who make the Cambodian Craft Beer Crown 2025 possible."
    :sponsors="sponsors"
  />
</template>

<script setup>
import SponsorSection from '@/components/SponsorSection.vue'

const sponsors = [
  { name: "BERTIE", logo: "/images/BERTIE.webp", description: "Official event partner." },
  { name: "BOTANICO", logo: "/images/botanico.webp", description: "Premium beer supplier." },
  { name: "CRAFT BEER ASSOCIATION", logo: "/images/CRAFT BEER ASSOCIATION.webp", description: "Local food provider." },
  { name: "THAI TAN", logo: "/images/thai tan.webp", description: "Community supporter." },
  { name: "YAKIMA CHIEF", logo: "/images/YAKIMA CHIEF.webp", description: "Craft beer enthusiast group." },
  { name: "SKAI TECH", logo: "/images/SKAI_Tech.webp", description: "Event logistics partner." }
]
</script>