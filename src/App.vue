<template>
  <div>
    <div class="stars-container">
      <div class="star star-1"></div>
      <div class="star star-2"></div>
      <div class="star star-3"></div>
      <div class="star star-4"></div>
      <div class="star star-5"></div>
      <div class="star star-6"></div>
      <div class="star star-7"></div>
      <div class="star star-8"></div>
      <div class="star star-9"></div>
      <div class="star star-10"></div>
      <div class="star star-11"></div>
      <div class="star star-12"></div>
      <div class="star star-13"></div>
      <div class="star star-14"></div>
      <div class="star star-15"></div>
      <div class="star star-16"></div>
      <div class="star star-17"></div>
      <div class="star star-18"></div>
      <div class="star star-19"></div>
      <div class="star star-20"></div>
      <div class="star star-21"></div>
      <div class="star star-22"></div>
      <div class="star star-23"></div>
      <div class="star star-24"></div>
      <div class="star star-25"></div>
      <div class="star star-26"></div>
      <div class="star star-27"></div>
      <div class="star star-28"></div>
      <div class="star star-29"></div>
      <div class="star star-30"></div>
      <div class="star star-31"></div>
      <div class="star star-32"></div>
      <div class="star star-33"></div>
      <div class="star star-34"></div>
      <div class="star star-35"></div>
      <div class="star star-36"></div>
      <div class="star star-37"></div>
      <div class="star star-38"></div>
      <div class="star star-39"></div>
      <div class="star star-40"></div>
    </div>
    <div id="app">
      <h1>Магический шар предсказаний</h1>
      <MagicBall />
    </div>
  </div>
</template>

<script>
import MagicBall from './components/MagicBall.vue'

export default {
  name: 'App',
  components: {
    MagicBall
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  position: relative;
  z-index: 10;
}

h1 {
  margin-bottom: 30px;
  color: #fff;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
  position: relative;
  z-index: 10;
}

/* Стили для звездного неба */
.stars-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: 1;
  pointer-events: none;
  background: linear-gradient(to bottom, #0b1026, #1a2145);
}

.star {
  position: absolute;
  width: 2px;
  height: 2px;
  background-color: #fff;
  border-radius: 50%;
  z-index: 1;
}

/* Позиции звезд */
.star-1 { top: 10%; left: 15%; width: 3px; height: 3px; animation: twinkle 5s infinite 0.1s; }
.star-2 { top: 20%; left: 25%; animation: twinkle 4s infinite 0.7s; }
.star-3 { top: 15%; left: 50%; width: 4px; height: 4px; animation: twinkle 6s infinite 1.2s; }
.star-4 { top: 30%; left: 75%; animation: twinkle 3.5s infinite 0.5s; }
.star-5 { top: 40%; left: 35%; width: 3px; height: 3px; animation: twinkle 4.5s infinite 0.3s; }
.star-6 { top: 50%; left: 60%; animation: twinkle 5.5s infinite 1.5s; }
.star-7 { top: 25%; left: 85%; width: 3px; height: 3px; animation: twinkle 4s infinite 0.2s; }
.star-8 { top: 60%; left: 10%; animation: twinkle 3s infinite 0.8s; }
.star-9 { top: 70%; left: 45%; width: 4px; height: 4px; animation: twinkle 6s infinite 1.3s; }
.star-10 { top: 80%; left: 70%; animation: twinkle 5s infinite 0.4s; }
.star-11 { top: 85%; left: 30%; width: 3px; height: 3px; animation: twinkle 4.5s infinite 1s; }
.star-12 { top: 75%; left: 90%; animation: twinkle 5.5s infinite 0.6s; }
.star-13 { top: 5%; left: 40%; width: 3px; height: 3px; animation: twinkle 5s infinite 1.4s; }
.star-14 { top: 35%; left: 5%; animation: twinkle 4s infinite 0.9s; }
.star-15 { top: 45%; left: 95%; width: 4px; height: 4px; animation: twinkle 6s infinite 1.1s; }
.star-16 { top: 55%; left: 20%; animation: twinkle 3.5s infinite 0.2s; }
.star-17 { top: 65%; left: 55%; width: 3px; height: 3px; animation: twinkle 4.5s infinite 1.7s; }
.star-18 { top: 90%; left: 15%; animation: twinkle 5.5s infinite 0.3s; }
.star-19 { top: 25%; left: 65%; width: 3px; height: 3px; animation: twinkle 4s infinite 1.9s; }
.star-20 { top: 95%; left: 80%; animation: twinkle 3s infinite 0.1s; }
.star-21 { top: 12%; left: 22%; animation: twinkle 4.2s infinite 0.4s; }
.star-22 { top: 28%; left: 8%; width: 3px; height: 3px; animation: twinkle 5.2s infinite 1.3s; }
.star-23 { top: 3%; left: 63%; animation: twinkle 3.7s infinite 0.7s; }
.star-24 { top: 47%; left: 83%; width: 4px; height: 4px; animation: twinkle 4.8s infinite 1.6s; }
.star-25 { top: 72%; left: 37%; animation: twinkle 5.8s infinite 0.9s; }
.star-26 { top: 88%; left: 52%; width: 3px; height: 3px; animation: twinkle 4.3s infinite 1.1s; }
.star-27 { top: 37%; left: 15%; animation: twinkle 3.3s infinite 0.5s; }
.star-28 { top: 62%; left: 77%; width: 3px; height: 3px; animation: twinkle 6.1s infinite 1.8s; }
.star-29 { top: 8%; left: 93%; animation: twinkle 4.9s infinite 0.3s; }
.star-30 { top: 53%; left: 42%; width: 4px; height: 4px; animation: twinkle 3.9s infinite 1.4s; }
.star-31 { top: 78%; left: 6%; animation: twinkle 5.4s infinite 0.8s; }
.star-32 { top: 93%; left: 27%; width: 3px; height: 3px; animation: twinkle 4.7s infinite 1.2s; }
.star-33 { top: 17%; left: 73%; animation: twinkle 3.6s infinite 0.6s; }
.star-34 { top: 42%; left: 97%; width: 3px; height: 3px; animation: twinkle 5.7s infinite 1.7s; }
.star-35 { top: 67%; left: 18%; animation: twinkle 4.1s infinite 0.2s; }
.star-36 { top: 83%; left: 58%; width: 4px; height: 4px; animation: twinkle 3.8s infinite 1.5s; }
.star-37 { top: 97%; left: 42%; animation: twinkle 5.3s infinite 0.9s; }
.star-38 { top: 22%; left: 88%; width: 3px; height: 3px; animation: twinkle 4.6s infinite 1.0s; }
.star-39 { top: 57%; left: 32%; animation: twinkle 3.4s infinite 0.4s; }
.star-40 { top: 73%; left: 67%; width: 3px; height: 3px; animation: twinkle 5.0s infinite 1.6s; }

/* Анимация мерцания */
@keyframes twinkle {
  0% { opacity: 0.2; }
  50% { opacity: 1; box-shadow: 0 0 5px #fff, 0 0 10px #fff; }
  100% { opacity: 0.2; }
}

body {
  margin: 0;
  padding: 0;
  height: 100%;
  overflow: hidden;
  background: transparent;
}

html {
  height: 100%;
}
</style>
