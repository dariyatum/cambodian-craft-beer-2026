<template>
  <div class="brewery-card">
    <div class="b-logo">
      <img :src="logo" :alt="name">
    </div>

    <h3>{{ name }}</h3>

    <p>{{ description }}</p>

    <a
      v-if="facebook !== 'NA'"
      :href="facebook"
      target="_blank"
      class="btn"
    >
      Meet Brewer
    </a>

    <span
      v-else
      class="btn disabled"
    >
      Coming Soon
    </span>
  </div>
</template>

<script setup>
defineProps({
  name: String,
  logo: String,
  description: String,
  facebook: String
})
</script>


<style scoped>
.brewery-card{
    background:#f8f0dc;
    border:3px solid #c89b3c;
    border-radius:18px;
    padding:25px;
    display:flex;
    flex-direction:column;
}

.b-logo{
    height:130px;
    display:flex;
    justify-content:center;
    align-items:center;
}

.b-logo img{
    width:100px;
    height:100px;
    object-fit:contain;
}

.btn{
    margin-top:auto;
}

.disabled{
    opacity:.6;
}
</style>