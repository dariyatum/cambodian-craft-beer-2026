<!-- Va -->
<template>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <header class="header">
    <div class="header-container">

      <div class="logo">
        <img src="/1.logo.webp" alt="Logo">
        <img src="/2.logo2.webp" alt="Logo">
      </div>

      <button
        class="hamburger"
        :class="{ 'is-active': isMenuOpen }"
        @click="isMenuOpen = !isMenuOpen"
        aria-label="Toggle menu"
      >
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </button>

      <nav class="nav-menu" :class="{ 'is-open': isMenuOpen }">
        <NuxtLink to="/" @click="isMenuOpen = false">Home</NuxtLink>
        <NuxtLink to="/breweries" @click="isMenuOpen = false">Breweries</NuxtLink>
        <NuxtLink to="/schedule" @click="isMenuOpen = false">Schedule</NuxtLink>
        <NuxtLink to="/beerstyle" @click="isMenuOpen = false">Beer Styles</NuxtLink>
        <NuxtLink to="/award" @click="isMenuOpen = false">Awards</NuxtLink>
        <NuxtLink to="/sponsor" @click="isMenuOpen = false">Sponsors</NuxtLink>
        <a href="https://docs.google.com/forms/d/e/1FAIpQLScEjueBWitDWygOZkaHDnkADWIHhYdgZ-lH_u3EvKM2RzL1AA/viewform" class="vote-btn mobile-vote-btn" @click="isMenuOpen = false">Judge Here</a>
      </nav>

      <a href="https://docs.google.com/forms/d/e/1FAIpQLScEjueBWitDWygOZkaHDnkADWIHhYdgZ-lH_u3EvKM2RzL1AA/viewform" class="vote-btn desktop-vote-btn">Judge Here</a>

    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
const isMenuOpen = ref(false)
</script>

<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.header {
  font-family: 'Inter', sans-serif;
  background: #ede5d0;
  border-bottom: 1px solid rgba(200, 155, 60, 0.3);
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 32px;
  height: 68px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 32px;
}

/* ── Logo ── */
.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-shrink: 0;
}

.logo img {
  width: 52px;
  height: 52px;
  object-fit: contain;
}

/* ── Nav ── */
.nav-menu {
  display: flex;
  align-items: center;
  gap: 32px;
}

.nav-menu a {
  text-decoration: none;
  color: #3b2417;
  font-size: 0.875rem;
  font-weight: 600;
  letter-spacing: 0.3px;
  transition: color 0.2s ease;
  white-space: nowrap;
}

.nav-menu a:hover {
  color: #7e2527;
}

.nav-menu a.router-link-active {
  color: #7e2527;
}

/* ── Judge button ── */
.vote-btn {
  display: inline-block;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(215, 163, 50, 0.6);
  border-radius: 8px;
  padding: 9px 20px;
  font-size: 0.875rem;
  font-weight: 700;
  text-decoration: none;
  cursor: pointer;
  white-space: nowrap;
  transition: background 0.2s ease, transform 0.15s ease;
  flex-shrink: 0;
}

.vote-btn:hover {
  background: #5c1b1d;
  transform: translateY(-1px);
}

/* ── Hamburger ── */
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 22px;
  height: 16px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  flex-shrink: 0;
}

.bar {
  width: 100%;
  height: 2px;
  background: #3b2417;
  border-radius: 2px;
  transition: transform 0.25s ease, opacity 0.25s ease;
}

.hamburger.is-active .bar:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.is-active .bar:nth-child(2) { opacity: 0; }
.hamburger.is-active .bar:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

.mobile-vote-btn { display: none; }

/* ── Tablet ── */
@media (max-width: 1024px) {
  .nav-menu { gap: 20px; }
}

/* ── Mobile ── */
@media (max-width: 768px) {
  .header-container {
    padding: 0 20px;
    height: 60px;
  }

  .hamburger { display: flex; }
  .desktop-vote-btn { display: none; }
  .mobile-vote-btn {
  display: block;
  margin-top: 8px;
  text-align: center;
  width: 100%;
  color: #f8e7c1 !important; /* Same as desktop */
}
.mobile-vote-btn,
.mobile-vote-btn:visited,
.mobile-vote-btn:hover,
.mobile-vote-btn:active {
  color: #f8e7c1 !important;
}

  .nav-menu {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background: #ede5d0;
    border-bottom: 1px solid rgba(200, 155, 60, 0.3);
    flex-direction: column;
    align-items: flex-start;
    gap: 0;
    padding: 0 20px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease, padding 0.3s ease;
  }

  .nav-menu.is-open {
    max-height: 420px;
    padding: 12px 20px 20px;
  }

  .nav-menu a:not(.mobile-vote-btn) {
    width: 100%;
    padding: 12px 0;
    font-size: 1rem;
    border-bottom: 1px solid rgba(59, 36, 23, 0.08);
  }

  .nav-menu a:last-of-type {
    border-bottom: none;
  }
}
</style>