<template>
   
  <div class="container">
    <header class="page-header">
      <h1 class="title">Meet The Brewers</h1>
      <div class="divider">❦ ❦ ❦</div>
    </header>

    <BreweryList />
  </div>
</template>

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

/* ── Layout ── */
.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 72px 32px 96px;
}

.page-header {
  margin-bottom: 56px;
}

/* ── Title ── */
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

/* ── Grid ── */
.brewery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px;
}

/* ── Card ── */
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

/* ── Logo ── */
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

/* ── Card text ── */
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

/* ── Button ── */
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

/* ── Responsive ── */
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
</style>