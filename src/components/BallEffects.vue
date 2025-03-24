<template>
  <div class="ball-effects">
    <div class="mystic-light" :class="{ 'active': showMysticLight }"></div>
    <div class="crystal-reflection"></div>
    <div class="reflection"></div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  showMysticLight: {
    type: Boolean,
    default: false
  }
});
</script>

<style scoped>
@import '../assets/animations.css';

.ball-effects {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  pointer-events: none;
  overflow: hidden;
}

.mystic-light {
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: radial-gradient(circle at center, rgba(30, 144, 255, 0), rgba(30, 144, 255, 0));
  opacity: 0;
  transition: all 0.5s ease;
  z-index: 3;
  pointer-events: none;
}

.mystic-light.active {
  opacity: 1;
  box-shadow: 0 0 80px 20px rgba(30, 144, 255, 0.6),
              inset 0 0 40px rgba(30, 144, 255, 0.4);
  background: radial-gradient(circle at center, rgba(30, 144, 255, 0.1), rgba(30, 144, 255, 0));
  animation: pulse 2s infinite;
}

.crystal-reflection {
  position: absolute;
  top: 15%;
  left: 20%;
  width: 40px;
  height: 10px;
  background: rgba(255, 255, 255, 0.7);
  border-radius: 50%;
  transform: rotate(30deg);
  filter: blur(3px);
}

.reflection {
  position: absolute;
  bottom: 20%;
  right: 20%;
  width: 70px;
  height: 20px;
  background: linear-gradient(rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border-radius: 50%;
  transform: rotate(-20deg);
  filter: blur(2px);
}

@keyframes pulse {
  0% { box-shadow: 0 0 60px 15px rgba(30, 144, 255, 0.6), inset 0 0 30px rgba(30, 144, 255, 0.4); }
  50% { box-shadow: 0 0 80px 25px rgba(30, 144, 255, 0.8), inset 0 0 40px rgba(30, 144, 255, 0.6); }
  100% { box-shadow: 0 0 60px 15px rgba(30, 144, 255, 0.6), inset 0 0 30px rgba(30, 144, 255, 0.4); }
}
</style>
