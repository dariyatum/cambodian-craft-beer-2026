<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>

  <div class="schedule-page">

    <!-- Hero -->
    <section class="hero">
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

    <!-- Schedule -->
    <section class="schedule-section">
      <div class="schedule-list">
        <EventScheduleItem icon="fa-regular fa-clock"        title="Event Begins"                      time="2:00 PM"  />
        <EventScheduleItem icon="fa-solid fa-users"          title="Introduction by the MC"            time="3:15 PM"  />
        <EventScheduleItem icon="fa-solid fa-music"          title="DJ Wha-Wah"                        time="3:30 PM"  />
        <EventScheduleItem icon="fa-solid fa-award"          title="Blind Tasting Live Session"        time="6:40 PM"  />
        <EventScheduleItem icon="fa-solid fa-award"          title="Award Ceremony Begins"             time="7:30 PM"  />
        <EventScheduleItem icon="fa-solid fa-music"          title="Live Music — The Broken Cymbal"    time="8:30 PM"  />
        <EventScheduleItem icon="fa-solid fa-business-time"  title="Event Ends"                        time="11:30 PM" />
      </div>
    </section>

  </div>
</template>

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

/* ── Hero ── */
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

/* ── Schedule ── */
.schedule-section {
  max-width: 680px;
  margin: 0 auto;
}

.schedule-list {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

/* ── Responsive ── */
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