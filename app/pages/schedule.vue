<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>

  <div class="schedule-page">

    <section class="hero reveal">
      <div class="hero__image">
        <img src="/images/bg-beer.jpg" alt="Event schedule" />
      </div>
      <div class="hero__content">
        <p class="eyebrow">❦ Craft Beer ❦</p>
        <h1 class="hero__title">Event Schedule</h1>
        <p class="hero__body">
          Join us for unforgettable beer experiences, brewery tours, tasting sessions, and community gatherings.
          Whether you're a craft beer enthusiast or just beginning your journey, our events offer the perfect
          opportunity to explore unique flavors and create memorable moments.
        </p>
      </div>
    </section>

    <section class="schedule-section">
      <div class="schedule-list">
        <EventScheduleItem class="reveal-card" style="--delay: 0ms"   icon="fa-regular fa-clock"       title="Event Begins"                   time="2:00 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 80ms"  icon="fa-solid fa-users"         title="Introduction by the MC"         time="3:15 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 160ms" icon="fa-solid fa-music"         title="DJ Wha-Wah"                     time="3:30 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 240ms" icon="fa-brands fa-hotjar"         title="Blind Tasting Live Session"     time="6:40 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 320ms" icon="fa-solid fa-award"         title="Award Ceremony Begins"          time="7:30 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 400ms" icon="fa-solid fa-music"         title="Live Music — The Broken Cymbal" time="8:30 PM"  />
        <EventScheduleItem class="reveal-card" style="--delay: 480ms" icon="fa-solid fa-business-time" title="Event Ends"                     time="11:30 PM" />
      </div>
    </section>

  </div>
</template>

<script setup>
import { onMounted } from 'vue'

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
  document.querySelectorAll('.reveal, .reveal-card').forEach(el => observer.observe(el))
})
</script>

<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.schedule-page {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  padding: 64px 24px 80px;
  max-width: 1080px;
  margin: 0 auto;
}

.hero {
  display: flex;
  align-items: center;
  gap: 56px;
  margin-bottom: 64px;
}

.hero__image {
  flex: 1;
  min-width: 0;
}

.hero__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 16px;
  display: block;
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.2);
}

.hero__content {
  flex: 1;
  min-width: 0;
}

.eyebrow {
  font-size: 0.8125rem;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 12px;
}

.hero__title {
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 900;
  color: #f8e7c1;
  text-transform: uppercase;
  letter-spacing: 4px;
  line-height: 1;
  margin-bottom: 20px;
}

.hero__body {
  font-size: 1rem;
  color: rgba(248, 231, 193, 0.75);
  line-height: 1.75;
}

.schedule-section {
  max-width: 680px;
  margin: 0 auto;
}

.schedule-list {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

/* Animations */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.55s ease, transform 0.55s ease;
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.reveal-card {
  opacity: 0;
  transform: translateX(-16px);
  transition:
    opacity 0.4s ease var(--delay, 0ms),
    transform 0.4s ease var(--delay, 0ms);
}

.reveal-card.is-visible {
  opacity: 1;
  transform: translateX(0);
}

@media (prefers-reduced-motion: reduce) {
  .reveal,
  .reveal-card {
    opacity: 1;
    transform: none;
    transition: none;
  }
}

@media (max-width: 768px) {
  .schedule-page {
    padding: 48px 16px 64px;
  }

  .hero {
    flex-direction: column;
    gap: 32px;
    margin-bottom: 48px;
  }

  .hero__image img {
    border-radius: 12px;
    max-height: 260px;
  }

  .hero__content {
    text-align: center;
  }
}
</style>