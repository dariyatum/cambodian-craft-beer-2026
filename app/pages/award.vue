<template>
  <Header />
  <div class="competition-wrapper">
    <div class="main-content">
      <div class="section-title-block">
        <h1 class="main-title">
          Competition Awards
        </h1>
        <p class="subtitle">
          Three prestigious categories await our winners
        </p>
      </div>

      <div class="awards-grid">
        
        <div class="award-card">
          <div class="icon-container">
            <svg class="award-svg" fill="currentColor" viewBox="0 0 24 24">
              <path d="M2 4l3 6 7-6 7 6 3-6v15H2V4zm1 2.22V17h18V6.22l-2.42 4.84-6.58-5.64-6.58 5.64L3 6.22zM4 14h16v1H4v-1z"/>
            </svg>
          </div>
          
          <h2 class="card-title">Main Award</h2>
          <span class="badge">
            Gold, Silver & Bronze
          </span>
          <p class="card-description description-fixed-width">
            This award is judged by a group of six international experts, according to the BJCP score sheet in a blind tasting mode. Some of the judges are BJCP certified.
          </p>
          
          <div class="medal-tier-box">
            <div class="medal-item">
              <span class="emoji">🏅</span>
              <span class="medal-label">Gold</span>
            </div>
            <div class="medal-item">
              <span class="emoji">🏅</span>
              <span class="medal-label">Silver</span>
            </div>
            <div class="medal-item">
              <span class="emoji">🏅</span>
              <span class="medal-label">Bronze</span>
            </div>
          </div>
        </div>

        <div class="award-card">
          <div class="icon-container">
            <svg class="award-svg" fill="currentColor" viewBox="0 0 24 24">
              <path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5s-3 1.34-3 3 1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5 5 1.34 5 3s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 2 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/>
            </svg>
          </div>
          
          <h2 class="card-title">People's Choice Award</h2>
          <span class="badge">
            Voted by all guests
          </span>
          <p class="card-description description-fixed-width">
            This is the award judged by you – all our guests. To judge, please use the judging form on this website and submit one judging per beer.
          </p>

          <div class="medal-tier-box layout-spacer"></div>
        </div>


          
          <div class="medal-tier-box layout-spacer"></div>
        </div>

      

        <div class="award-card">
          <div class="icon-container">
            <svg class="award-svg" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20 6h-2.18c.11-.31.18-.65.18-1 0-1.66-1.34-3-3-3-1.05 0-1.96.54-2.5 1.35l-.5.65-.5-.65C10.96 2.54 10.05 2 9 2 7.34 2 6 3.34 6 5c0 .35.07.69.18 1H4c-1.11 0-1.99.89-1.99 2L2 19c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V8c0-1.11-.89-2-2-2zm-5-2c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zM9 4c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm11 15H4V8h16v11z"/>
            </svg>
          </div>
          
          <h2 class="card-title">Brewer's Choice Award</h2>
          <span class="badge">
            Voted by participating brewers
          </span>
          <p class="card-description description-fixed-width">
            All brewers participating are also present at the event. The brewers judge their fellow competitors' creations.
          </p>
          
          <div class="medal-tier-box layout-spacer"></div>
        </div>

      </div>
    </div>


    <footer class="footer">
      © CBAC — Cambodian Craft Beer Association • Event: 16 August 2025 • Botanico Craft Beer Garden
    </footer>
  </div>
</template>

<style scoped>
.competition-wrapper {
  background-color: #FAF6F0;
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #1A1A1A;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.main-content {
  max-width: 1152px; 
  margin-left: auto;
  margin-right: auto;
  padding-left: 20px; 
  padding-right: 20px;
  padding-top: 48px;
  padding-bottom: 48px;
  width: 100%;
  box-sizing: border-box;
}

.section-title-block {
  text-align: center;
  margin-bottom: 40px;
}

.main-title {
  font-size: 28px; 
  font-weight: 400;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: #000000;
  margin-bottom: 8px;
  margin-top: 0;
}

.subtitle {
  font-size: 14px; 
  font-weight: 500;
  letter-spacing: 0.05em;
  color: rgba(0, 0, 0, 0.8);
  margin: 0;
}


/* 1. Base style (Mobile First: Default is 1 column) */
.awards-grid {
  display: grid;
  grid-template-columns: repeat(1, minmax(0, 1fr)); /* 1 column on mobile */

.awards-grid {
  display: grid;
  grid-template-columns: repeat(1, minmax(0, 1fr));
  gap: 24px;
  margin-bottom: 48px;
}


/* 2. Desktop/Tablet override (Triggers only on screens wider than 768px) */
@media (min-width: 768px) {
  .awards-grid {
    grid-template-columns: repeat(3, minmax(0, 1fr)); /* 3 columns on desktop */
  }
}

/* 3. Mobile adjustments (Screens smaller than 768px) */
@media (max-width: 767px) {
  .layout-spacer {
    display: none; /* Hides the dead space spacers on mobile layout */
  }
  .main-title {
    font-size: 24px; 
  }
}


.award-card {
  background-color: #F5EDE0;
  border-radius: 12px;
  padding: 32px 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  box-sizing: border-box;
}

.icon-container {
  margin-bottom: 12px;
  color: #000000;
}

.award-svg {
  width: 40px;
  height: 40px;
}

.card-title {
  font-size: 18px; 
  font-weight: 600;
  color: #000000;
  margin-bottom: 4px;
  margin-top: 0;
}

.badge {
  display: inline-block;
  background-color: #FFFFFF;
  font-size: 11px; 
  font-weight: 500;
  padding: 4px 14px;
  border-radius: 9999px;
  color: rgba(0, 0, 0, 0.8);
  margin-bottom: 16px;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
}

.card-description {
  font-size: 13px; 
  line-height: 1.6;
  color: rgba(0, 0, 0, 0.9);
  margin: 0;
}

.description-fixed-width {
  max-width: 280px; 
}

.medal-tier-box {
  margin-top: auto;
  display: flex;
  justify-content: center;
  gap: 24px;
  padding-top: 24px;
  width: 100%;
}


.layout-spacer {
  height: 49px; 
}

.medal-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
}

.emoji {
  font-size: 20px;
}

.medal-label {
  font-size: 12px;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.8);
}

.footer {
  background-color: #7A1E11;
  color: #EAEAEA;
  text-align: center;
  padding: 16px 20px;
  font-size: 11px;
  line-height: 1.5;
  letter-spacing: 0.05em;
  width: 100%;
  box-sizing: border-box;
}


@media (min-width: 768px) {
  .awards-grid {

    grid-template-cols: repeat(3, minmax(0, 1fr));
  }
}

@media (max-width: 768px) {
  .layout-spacer {
    display: none; 

    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}


@media (max-width: 767px) {
  .layout-spacer {
    display: none;

  }
  .main-title {
    font-size: 24px; 
  }
}
</style>