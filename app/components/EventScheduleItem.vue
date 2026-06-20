<script setup>
defineProps({
  icon: String,
  title: String,
  time: String,
})
</script>

<template>
  <div class="event-card">
    <div class="event-icon">
      <i :class="icon"></i>
    </div>

    <h3 class="event-title">
      {{ title }}
    </h3>

    <span class="event-time">
      {{ time }}
    </span>
  </div>
</template>

<style scoped>
.event-card {
  display: flex;
  align-items: center;
  justify-content: space-between;

  width: 100%;
  min-height: 110px;

  padding: 0 2rem;

  background: #852d1f;
  border-radius: 24px;

  color: white;

  transition: all .3s ease;
}

.event-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 15px 35px rgba(0,0,0,.2);
}

.event-icon {
  width: 72px;
  height: 72px;

  border-radius: 50%;

  background: #d4a017;

  display: flex;
  align-items: center;
  justify-content: center;

  flex-shrink: 0;
}

.event-icon i {
  font-size: 2rem;
  color: white;
}

.event-title {
  flex: 1;

  text-align: center;

  font-size: 2rem;
  font-weight: 500;
}

.event-time {
  font-size: 2rem;
  font-weight: 500;
}
</style>