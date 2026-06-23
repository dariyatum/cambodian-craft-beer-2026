<template>
  <div class="brewery-card reveal-card" :style="{ '--delay': `${index * 80}ms` }">
    <div class="b-logo">
      <img :src="logo" :alt="name">
    </div>

    <h3>{{ name }}</h3>

    <p>{{ description }}</p>

    
     <a v-if="facebook !== 'NA'"
      :href="facebook"
      target="_blank"
      class="btn"
    >
      Meet Brewer
    </a>

    <span v-else class="btn disabled">
      Coming Soon
    </span>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const props = defineProps({
  name: String,
  logo: String,
  description: String,
  facebook: String,
  index: { type: Number, default: 0 }
})

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
  document.querySelectorAll('.reveal-card').forEach(el => observer.observe(el))
})

</script>

<style scoped>
.brewery-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 32px 28px 28px;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.brewery-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.16);
}

.b-logo {
  display: flex;
  justify-content: center;
  margin-bottom: 24px;
}

.b-logo img {
  width: 80px;
  height: 80px;
  object-fit: contain;
  background: #fffaf0;
  border-radius: 50%;
  border: 2px solid rgba(200, 155, 60, 0.55);
  padding: 10px;
}

.brewery-card h3 {
  font-size: 1.125rem;
  font-weight: 700;
  color: #1e1108;
  margin-bottom: 10px;
  line-height: 1.3;
}

.brewery-card p {
  font-size: 0.9375rem;
  color: #4d3b2c;
  line-height: 1.7;
  flex-grow: 1;
  margin-bottom: 28px;
}

.btn {
  display: block;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(200, 155, 60, 0.65);
  border-radius: 8px;
  padding: 13px 20px;
  font-size: 0.9375rem;
  font-weight: 600;
  letter-spacing: 0.3px;
  text-decoration: none;
  text-align: center;
  transition: background 0.2s ease, transform 0.15s ease;
  margin-top: auto;
}

.btn:hover {
  background: #5f1b1d;
  transform: translateY(-1px);
}

.disabled {
  opacity: 0.6;
  cursor: default;
}

.disabled:hover {
  background: #7e2527;
  transform: none;
}

/* Animation */
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
  .reveal-card {
    opacity: 1;
    transform: none;
    transition: none;
  }
}
</style>