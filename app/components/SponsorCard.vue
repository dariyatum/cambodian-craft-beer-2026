<template>
  <div class="sponsor-card">
    <img :src="sponsor.logo" :alt="sponsor.name" loading="lazy" />
    <h3>{{ sponsor.name }}</h3>
    <p>{{ sponsor.description }}</p>
  </div>
</template>

<script setup>
defineProps({
  sponsor: {
    type: Object,
    required: true,
    validator: (s) => 'name' in s && 'logo' in s && 'description' in s
  }
})
</script>

<style scoped>
.sponsor-card {
  background: #e8dfcf;
  border-radius: 12px;
  padding: 30px 20px;
  transition: 0.3s ease;
  font-family: 'Inter', sans-serif;
}

.sponsor-card:hover {
  transform: translateY(-5px);
}

.sponsor-card img {
  width: 180px;
  height: 180px;
  object-fit: contain;
}

.sponsor-card h3 {
  font-size: 16px;
  font-weight: 700;
  margin-bottom: 8px;
}

.sponsor-card p {
  font-size: 14px;
  color: #444;
}
</style>