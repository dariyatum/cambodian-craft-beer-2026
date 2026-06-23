<template>
  <div class="brewery-grid">
    <BreweryCard
      v-for="(brewery, index) in breweries"
      :key="brewery.name"
      :name="brewery.name"
      :logo="brewery.logo"
      :description="brewery.description"
      :facebook="brewery.facebook"
      :index="index"
    />
  </div>
</template>

<script setup>
import breweries from '../data/breweries'
</script>