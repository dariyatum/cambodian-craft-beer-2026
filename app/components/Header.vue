<template>
  <header class="header">
    <div class="header-container">

      <div class="logo">
        <img src="/1.logo-removebg-preview.png" alt="Logo">
      </div>

      <nav class="nav-menu">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/brewery">Brewery</NuxtLink>
        <NuxtLink to="/schedule">Schedule</NuxtLink>
        <NuxtLink to="/schedule">Beer Style</NuxtLink>
        <NuxtLink to="/award">Award</NuxtLink>
        <NuxtLink to="/sponsor">Sponsor</NuxtLink>
      </nav>


      <button class="vote-btn">
        Vote
      </button>

    </div>
  </header>
</template>


<style scoped>

html, body {
  font-family: 'Inter', sans-serif;
}

</style>


<style scoped>
.header {
  background-color: #e8dfcc;
  height: 60px;
  border-bottom: 1px solid #ddd;

}

.header-container {
  max-width: 1200px;
  height: 100%;
  margin: 0;
  padding: 0 30px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo img {
  width: 80px;
  height: 80px;
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
}

.vote-btn:hover {
  background-color: #b8860b;
}
</style>