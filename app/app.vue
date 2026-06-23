<template>

  <div>
  
    <Header/>
    <NuxtPage />
      <NuxtFooter />
  </div>

</template>

<style>
html,
body {
  margin: 0;
  padding: 0;
  font-family: 'Inter', sans-serif;
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
    url('/background.jpeg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  min-height: 100vh;
}
</style>