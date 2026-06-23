<template>
  <Header />

  <div class="award-page">
    <div class="award-page__hero">
      <p class="award-page__eyebrow">❦ Cambodia Craft Beer Crown 2026 ❦</p>
      <h1 class="award-page__title">Competition Awards</h1>
      <p class="award-page__subtitle">Three prestigious categories await our winners</p>
    </div>

    <div class="awards-grid">

      <!-- Main Award -->
      <div class="award-card">
        <div class="award-card__icon">
          <svg fill="currentColor" viewBox="0 0 24 24">
            <path d="M2 4l3 6 7-6 7 6 3-6v15H2V4zm1 2.22V17h18V6.22l-2.42 4.84-6.58-5.64-6.58 5.64L3 6.22zM4 14h16v1H4v-1z"/>
          </svg>
        </div>
        <p class="award-card__eyebrow">Gold, Silver & Bronze</p>
        <h2 class="award-card__title">Main Award</h2>
        <p class="award-card__description">
          Judged by six international experts using the BJCP score sheet in blind tasting mode. Some judges are BJCP certified.
        </p>
        <div class="medal-row">
          <div class="medal-item">
            <span class="medal medal--gold">G</span>
            <span class="medal-label">Gold</span>
          </div>
          <div class="medal-item">
            <span class="medal medal--silver">S</span>
            <span class="medal-label">Silver</span>
          </div>
          <div class="medal-item">
            <span class="medal medal--bronze">B</span>
            <span class="medal-label">Bronze</span>
          </div>
        </div>
      </div>

      <!-- People's Choice -->
      <div class="award-card">
        <div class="award-card__icon">
          <svg fill="currentColor" viewBox="0 0 24 24">
            <path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5s-3 1.34-3 3 1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 2 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/>
          </svg>
        </div>
        <p class="award-card__eyebrow">Voted by all guests</p>
        <h2 class="award-card__title">People's Choice</h2>
        <p class="award-card__description">
          Judged by you — all our guests. Use the judging form on this website and submit one vote per beer.
        </p>
      </div>

      <!-- Brewer's Choice -->
      <div class="award-card">
        <div class="award-card__icon">
          <svg fill="currentColor" viewBox="0 0 24 24">
            <path d="M20 6h-2.18c.11-.31.18-.65.18-1 0-1.66-1.34-3-3-3-1.05 0-1.96.54-2.5 1.35l-.5.65-.5-.65C10.96 2.54 10.05 2 9 2 7.34 2 6 3.34 6 5c0 .35.07.69.18 1H4c-1.11 0-1.99.89-1.99 2L2 19c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V8c0-1.11-.89-2-2-2zm-5-2c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zM9 4c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm11 15H4V8h16v11z"/>
          </svg>
        </div>
        <p class="award-card__eyebrow">Voted by participating brewers</p>
        <h2 class="award-card__title">Brewer's Choice</h2>
        <p class="award-card__description">
          All participating brewers are present at the event and judge their fellow competitors' creations.
        </p>
      </div>

    </div>

    <footer class="footer">
      © CBAC — Cambodian Craft Beer Association &nbsp;·&nbsp; 20 July 2026 &nbsp;·&nbsp; Botanico Craft Beer Garden
    </footer>
  </div>
</template>

<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.award-page {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* ── Hero ── */
.award-page__hero {
  max-width: 680px;
  margin: 0 auto;
  padding: 64px 24px 40px;
  text-align: left;
  width: 100%;
}

.award-page__eyebrow {
  font-size: 0.8125rem;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 12px;
}

.award-page__title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 900;
  color: #f8e7c1;
  text-transform: uppercase;
  letter-spacing: 4px;
  line-height: 1;
  margin-bottom: 14px;
}

.award-page__subtitle {
  font-size: 1rem;
  color: rgba(248, 231, 193, 0.75);
  line-height: 1.65;
}

/* ── Grid ── */
.awards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
  max-width: 1080px;
  margin: 0 auto;
  padding: 0 24px 64px;
  width: 100%;
  flex: 1;
}

/* ── Card ── */
.award-card {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 16px;
  padding: 32px 24px 28px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.award-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.14);
}

.award-card__icon {
  width: 56px;
  height: 56px;
  background: #7e2527;
  border: 1px solid rgba(215, 163, 50, 0.5);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #f8e7c1;
  margin-bottom: 16px;
  flex-shrink: 0;
}

.award-card__icon svg {
  width: 26px;
  height: 26px;
}

.award-card__eyebrow {
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #c89b3c;
  margin-bottom: 8px;
}

.award-card__title {
  font-size: 1.25rem;
  font-weight: 800;
  color: #2d1508;
  margin-bottom: 14px;
  line-height: 1.2;
}

.award-card__description {
  font-size: 0.9375rem;
  color: #4a2e1a;
  line-height: 1.7;
  max-width: 28ch;
}

/* ── Medals ── */
.medal-row {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 28px;
  padding-top: 24px;
  border-top: 1px solid rgba(200, 155, 60, 0.25);
  width: 100%;
}

.medal-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
}

.medal {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  font-weight: 800;
  color: white;
}

.medal--gold   { background: #c89b3c; }
.medal--silver { background: #8a9ba8; }
.medal--bronze { background: #a0634a; }

.medal-label {
  font-size: 0.75rem;
  font-weight: 600;
  color: #4a2e1a;
}

/* ── Footer ── */
.footer {
  background: #7e2527;
  color: rgba(248, 231, 193, 0.9);
  border-top: 1px solid rgba(215, 163, 50, 0.4);
  text-align: center;
  padding: 18px 24px;
  font-size: 0.8125rem;
  letter-spacing: 0.5px;
  line-height: 1.5;
}

/* ── Responsive ── */
@media (max-width: 640px) {
  .award-page__hero {
    padding: 48px 16px 32px;
  }
  .awards-grid {
    grid-template-columns: 1fr;
    padding: 0 16px 48px;
  }
}
</style>