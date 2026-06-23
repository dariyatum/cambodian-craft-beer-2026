<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

  <div class="home-page">

    <div class="passport-banner reveal">
      <span>🍺 Brewery Passport</span>
      <p>Visit all 11 breweries and discover your favorite beer.</p>
    </div>

    <section class="hero-card reveal" style="--delay: 100ms">
      <div class="hero-content">
        <h1>Cambodian Craft Beer Crown 2026</h1>
        <p>Cambodia's premier craft beer competition — 11 exceptional breweries competing for the crown.</p>
        <a href="https://docs.google.com/forms/d/e/1FAIpQLScEjueBWitDWygOZkaHDnkADWIHhYdgZ-lH_u3EvKM2RzL1AA/viewform" class="judge-btn">Judge Here</a>
      </div>
      <div class="hero-image">
        <img src="/images/beer.png" alt="Beer" />
      </div>
    </section>

    <section class="welcome-card reveal" style="--delay: 200ms">
      <h2>Welcome!</h2>
      <p>Thank you for being part of Cambodia Craft Beer Crown 2026.</p>
      <p class="event-details">20 July 2026 · 2:00 PM – 11:30 PM · Botanico Craft Beer Garden</p>
    </section>

    <section class="rules-section reveal" style="--delay: 300ms">
      <h2>How It Works</h2>
      <div class="rules-grid">

        <div class="rule reveal-card" style="--delay: 350ms">
          <div class="rule__step">1</div>
          <div class="rule__icon">
            <i class="fa-solid fa-beer-mug-empty"></i>
          </div>
          <h3>Taste</h3>
          <p>Taste each beer carefully.</p>
        </div>

        <div class="rule__connector">
          <div class="rule__line"></div>
          <i class="fa-solid fa-chevron-right rule__arrow"></i>
          <div class="rule__line"></div>
        </div>

        <div class="rule reveal-card" style="--delay: 430ms">
          <div class="rule__step">2</div>
          <div class="rule__icon">
            <i class="fa-solid fa-wine-glass"></i>
          </div>
          <h3>Evaluate</h3>
          <p>Consider aroma, flavor, balance, and overall impression.</p>
        </div>

        <div class="rule__connector">
          <div class="rule__line"></div>
          <i class="fa-solid fa-chevron-right rule__arrow"></i>
          <div class="rule__line"></div>
        </div>

        <div class="rule reveal-card" style="--delay: 510ms">
          <div class="rule__step">3</div>
          <div class="rule__icon">
            <i class="fa-solid fa-check-to-slot"></i>
          </div>
          <h3>Vote</h3>
          <p>Choose your favorite and submit your vote.</p>
        </div>

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

.home-page {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  padding: 24px 32px 64px;
  max-width: 900px;
  margin: 0 auto;
}

.passport-banner {
  background: #7e2527;
  border: 1px dashed rgba(215, 163, 50, 0.7);
  border-radius: 12px;
  text-align: center;
  padding: 16px 20px;
  margin-bottom: 20px;
}

.passport-banner span {
  display: block;
  color: #f8e7c1;
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 4px;
}

.passport-banner p {
  color: rgba(255, 255, 255, 0.85);
  font-size: 0.9375rem;
}

.hero-card {
  background: rgba(248, 240, 220, 0.95);
  border: 1px solid rgba(200, 155, 60, 0.5);
  border-radius: 20px;
  padding: 40px 36px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 32px;
  position: relative;
  overflow: hidden;
  margin-bottom: 20px;
}

.hero-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, #7e2527, #d7a332, #7e2527);
}

.hero-content {
  flex: 1;
}

.hero-content h1 {
  font-size: clamp(1.6rem, 3.5vw, 2.4rem);
  font-weight: 900;
  color: #2d1508;
  line-height: 1.15;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 14px;
}

.hero-content p {
  font-size: 1rem;
  color: #4a2e1a;
  line-height: 1.65;
  margin-bottom: 28px;
  max-width: 42ch;
}

.judge-btn {
  display: inline-block;
  background: #7e2527;
  color: #f8e7c1;
  border: 1px solid rgba(215, 163, 50, 0.7);
  border-radius: 10px;
  padding: 13px 28px;
  font-size: 1rem;
  font-weight: 700;
  text-decoration: none;
  transition: background 0.2s ease, transform 0.15s ease;
}

.judge-btn:hover {
  background: #5c1b1d;
  transform: translateY(-2px);
}

.hero-image img {
  width: 150px;
  filter: drop-shadow(0 8px 12px rgba(0, 0, 0, 0.25));
  animation: floatBeer 4s ease-in-out infinite;
  flex-shrink: 0;
}

@keyframes floatBeer {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.welcome-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 32px;
  text-align: center;
  margin-bottom: 20px;
}

.welcome-card h2 {
  font-size: 1.5rem;
  font-weight: 800;
  color: #2d1508;
  margin-bottom: 10px;
}

.welcome-card p {
  font-size: 1rem;
  color: #4a2e1a;
  line-height: 1.65;
}

.event-details {
  margin-top: 10px;
  font-size: 0.9375rem !important;
  color: #7e5a3a !important;
  font-weight: 500;
}

.rules-section {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 36px 32px;
}

.rules-section h2 {
  text-align: center;
  font-size: 1.5rem;
  font-weight: 800;
  color: #2d1508;
  margin-bottom: 32px;
}

.rules-grid {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0;
}

.rule {
  flex: 1;
  max-width: 200px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  background: #fff8ee;
  border: 1px solid rgba(200, 155, 60, 0.3);
  border-radius: 14px;
  padding: 24px 16px 20px;
  position: relative;
}

.rule__step {
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  width: 28px;
  height: 28px;
  background: #7e2527;
  border: 2px solid #fdf6e8;
  border-radius: 50%;
  color: #f8e7c1;
  font-size: 0.75rem;
  font-weight: 800;
  display: flex;
  align-items: center;
  justify-content: center;
}

.rule__icon {
  width: 56px;
  height: 56px;
  background: rgba(126, 37, 39, 0.08);
  border-radius: 50%;
  color: #7e2527;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  margin-bottom: 14px;
  margin-top: 8px;
  transition: background 0.2s ease, color 0.2s ease, transform 0.2s ease;
}

.rule:hover .rule__icon {
  background: #7e2527;
  color: #f8e7c1;
  transform: scale(1.08);
}

.rule h3 {
  font-size: 0.9375rem;
  font-weight: 800;
  color: #2d1508;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.rule p {
  font-size: 0.875rem;
  color: #4a2e1a;
  line-height: 1.6;
}

.rule__connector {
  display: flex;
  align-items: center;
  flex-shrink: 0;
  width: 40px;
}

.rule__line {
  flex: 1;
  height: 1px;
  background: rgba(200, 155, 60, 0.4);
}

.rule__arrow {
  color: #c89b3c;
  font-size: 0.625rem;
  padding: 0 2px;
}

/* Animations */
.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition:
    opacity 0.5s ease var(--delay, 0ms),
    transform 0.5s ease var(--delay, 0ms);
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.reveal-card {
  opacity: 0;
  transform: translateY(12px);
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

@media (max-width: 640px) {
  .home-page {
    padding: 16px 16px 48px;
  }

  .hero-card {
    flex-direction: column-reverse;
    text-align: center;
    padding: 28px 20px 24px;
    gap: 20px;
  }

  .hero-content p {
    max-width: 100%;
    margin-bottom: 20px;
  }

  .judge-btn {
    width: 100%;
    text-align: center;
    padding: 14px;
  }

  .hero-image img {
    width: 130px;
  }

  .welcome-card,
  .rules-section {
    padding: 24px 20px;
  }

  .rules-grid {
    flex-direction: column;
    gap: 0;
  }

  .rule {
    max-width: 100%;
    width: 100%;
  }

  .rule__connector {
    width: auto;
    height: 36px;
    flex-direction: column;
  }

  .rule__line {
    width: 1px;
    height: 100%;
    flex: 1;
  }

  .rule__arrow {
    transform: rotate(90deg);
  }
}
</style>