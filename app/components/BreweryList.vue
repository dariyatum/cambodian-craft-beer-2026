<template>

<div class="brewery-grid">

    <BreweryCard
        v-for="(brewery,index) in breweries"
        :key="brewery.name"
        :brewery="brewery"
        data-aos="zoom-in"
        :data-aos-delay="index*100"
    />

</div>

</template>

<script setup>

import breweries from "../data/breweries"
import BreweryCard from "./BreweryCard.vue"

</script>

<style scoped>

.brewery-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:24px;
}

</style>