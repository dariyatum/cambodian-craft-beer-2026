<template>
  <div class="schedule-item">
    <div class="schedule-item__icon">
      <i :class="icon"></i>
    </div>
    <div class="schedule-item__body">
      <p class="schedule-item__title">{{ title }}</p>
    </div>
    <span class="schedule-item__time">{{ time }}</span>
  </div>
</template>

<script setup>
defineProps({
  icon: String,
  title: String,
  time: String,
})
</script>

<style scoped>
.schedule-item {
  background: #fdf6e8;
  border: 1px solid rgba(200, 155, 60, 0.45);
  border-radius: 12px;
  padding: 18px 24px;
  display: flex;
  align-items: center;
  gap: 18px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.schedule-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
}

.schedule-item__icon {
  width: 44px;
  height: 44px;
  background: #7e2527;
  border: 1px solid rgba(215, 163, 50, 0.5);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #f8e7c1;
  font-size: 1rem;
  flex-shrink: 0;
}

.schedule-item__body {
  flex: 1;
  min-width: 0;
}

.schedule-item__title {
  font-size: 1rem;
  font-weight: 700;
  color: #2d1508;
  line-height: 1.3;
}

.schedule-item__time {
  font-size: 0.9375rem;
  font-weight: 700;
  color: #c89b3c;
  white-space: nowrap;
  flex-shrink: 0;
}
</style>