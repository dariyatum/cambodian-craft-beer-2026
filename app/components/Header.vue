<!-- Va -->
<template>
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
        <NuxtLink to="/brewery" @click="isMenuOpen = false">Brewery</NuxtLink>
        <NuxtLink to="/schedule" @click="isMenuOpen = false">Schedule</NuxtLink>
        <NuxtLink to="/schedule" @click="isMenuOpen = false">Beer Style</NuxtLink>
        <NuxtLink to="/award" @click="isMenuOpen = false">Award</NuxtLink>
        <NuxtLink to="/sponsor" @click="isMenuOpen = false">Sponsor</NuxtLink>
        
        <button class="vote-btn mobile-vote-btn">
          Judge Here
        </button>
      </nav>

      <button class="vote-btn desktop-vote-btn">
        Judge Here
      </button>

    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)
</script>

<style scoped>
html, body {
  font-family: 'Inter', sans-serif;
  margin: 0px;
  padding: 0px;
}

.header {
  background-color: #e8dfcc;
  min-height: 60px; 
  border-bottom: 1px solid #ddd;
  position: relative;
  z-index: 100;
}

.header-container {
  height: 100%;
  margin: 0;
  padding: 0 30px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 5px;
  padding-bottom: 5px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo img {
  width: 80px;
  height: 70px;
  margin-top: 10px;
  object-fit: contain;
}

.nav-menu {
  display: flex;
  gap: 60px;
}

.nav-menu a {
  text-decoration: none;
  color: #333;
  font-size: 12px;
  font-weight: 600;
  transition: color 0.3s;
}

.nav-menu a:hover {
  color: #b8860b;
}

.vote-btn {
  background-color: #7e2527;
  color: white;
  border: none;
  padding: 8px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 12px;
  white-space: nowrap;
  transition: background-color 0.3s;
}

.vote-btn:hover {
  background-color: #b8860b;
}

/* Hidden by default on desktop layout */
.hamburger {
  display: none;
}
.mobile-vote-btn {
  display: none;
}

/* ==========================================
   MEDIA QUERIES (The Responsive Magic)
   ========================================== */

/* For Tablets and smaller desktops */
@media (max-width: 1024px) {
  .nav-menu {
    gap: 30px; 
  }
}

/* For Mobile Devices */
@media (max-width: 768px) {
  .header-container {
    padding: 0 20px;
  }

  .desktop-vote-btn {
    display: none; /* Hide the normal button position */
  }

  .mobile-vote-btn {
    display: block; /* Show button inside mobile dropdown list */
    margin-top: 20px;
    width: 100%;
    text-align: center;
  }

  /* Hamburger Icon Styling (Pure CSS) */
  .hamburger {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 24px;
    height: 18px;
    background: transparent;
    border: none;
    cursor: pointer;
    padding: 0;
    z-index: 101;
  }

  .hamburger .bar {
    width: 100%;
    height: 2px;
    background-color: #333;
    transition: all 0.3s ease-in-out;
  }

  /* Hamburger to "X" Animation when open */
  .hamburger.is-active .bar:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
  }
  
  .hamburger.is-active .bar:nth-child(2) {
    opacity: 0;
  }
  
  .hamburger.is-active .bar:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
  }

  /* Mobile Dropdown Drawer Menu */
  .nav-menu {
    position: absolute;
    top: 100%; /* Sits directly beneath the header */
    left: 0;
    width: 100%;
    background-color: #e8dfcc;
    border-bottom: 1px solid #ddd;
    flex-direction: column;
    gap: 0;
    padding: 0;
    max-height: 0; /* Hidden by default via height */
    overflow: hidden;
    transition: max-height 0.3s ease-in-out, padding 0.3s ease-in-out;
  }

  /* When Hamburger triggers the 'is-open' class */
  .nav-menu.is-open {
    max-height: 400px; /* Big enough to container all links */
    padding: 20px;
  }

  .nav-menu a {
    width: 100%;
    padding: 12px 0;
    font-size: 16px; /* Slightly larger targets for thumbs */
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  }
  
  .nav-menu a:last-of-type {
    border-bottom: none;
  }
}
</style>