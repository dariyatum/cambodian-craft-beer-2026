<template>
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />

  <div class="container">

    <header class="page-header reveal">
      <h1 class="title">Meet The Brewers</h1>
      <div class="divider">❦ ❦ ❦</div>
    </header>

    <BreweryList />

<button
  class="back-to-top"
  :class="{ 'is-visible': showBtn }"
  @click="scrollToTop"
  aria-label="Back to top"
>
  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
    <polyline points="18 15 12 9 6 15"/>
  </svg>
</button>

  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const showBtn = ref(false)

function onScroll() {
  showBtn.value = window.scrollY > 300
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', onScroll)

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

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<style>
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  line-height: 1.6;
  background:
    linear-gradient(
      160deg,
      rgba(100, 45, 30, 0.92) 0%,
      rgba(195, 130, 90, 0.88) 100%
    ),
    url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  min-height: 100vh;
}

.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 72px 32px 96px;
}

.page-header {
  margin-bottom: 56px;
}

.title {
  color: #f8e7c1;
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 800;
  letter-spacing: 6px;
  text-transform: uppercase;
  line-height: 1;
  margin-bottom: 20px;
}

.divider {
  color: #c89b3c;
  font-size: 1.25rem;
  letter-spacing: 8px;
}

.brewery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px;
}

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
}

.btn:hover {
  background: #5f1b1d;
  transform: translateY(-1px);
}

/* Animations */
.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
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

/* Back to top */
.back-to-top {
  position: fixed;
  bottom: 32px;
  right: 32px;
  width: 44px;
  height: 44px;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(215, 163, 50, 0.6);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.875rem;
  cursor: pointer;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.25);
  opacity: 0;
  transform: translateY(12px);
  transition: opacity 0.25s ease, transform 0.25s ease, background 0.2s ease;
  pointer-events: none;
  z-index: 50;
}

.back-to-top.is-visible {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}

.back-to-top:hover {
  background: #5c1b1d;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .container {
    padding: 48px 20px 64px;
  }

  .page-header {
    margin-bottom: 40px;
  }

  .brewery-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .brewery-card {
    padding: 24px 20px 20px;
  }
}

@media (max-width: 640px) {
  .back-to-top {
    bottom: 20px;
    right: 20px;
    width: 40px;
    height: 40px;
  }
}
</style>