<template>
  <div class="magic-ball-container">
    <div class="magic-ball" 
         @click="shakeBall" 
         :class="{ 'shaking': isShaking }">
      <BallEffects 
        :showMysticLight="showMysticLight" 
      />
      <div class="black-circle">
        <AnswerCircle 
          :showAnswer="showAnswer" 
          :answerText="currentAnswer"
          :showBubbles="showBubbles" 
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onUnmounted } from 'vue';
import AnswerCircle from './AnswerCircle.vue';
import BallEffects from './BallEffects.vue';
import AnswerService from '../services/AnswerService';

const isShaking = ref(false);
const showAnswer = ref(false);
const showMysticLight = ref(false);
const showBubbles = ref(false);
const currentAnswer = ref('');
let shakingTimeout = null;

const shakeBall = () => {
  if (isShaking.value) return;
  
  showAnswer.value = false;
  showMysticLight.value = false;
  
  isShaking.value = true;
  showBubbles.value = true;
  
  currentAnswer.value = AnswerService.getRandomAnswer();
  
  shakingTimeout = setTimeout(() => {
    isShaking.value = false;
    showBubbles.value = false;
    
    showMysticLight.value = true;
    showAnswer.value = true;
    
    setTimeout(() => {
      showMysticLight.value = false;
    }, 3000);
  }, 1200);
};

onUnmounted(() => {
  if (shakingTimeout) clearTimeout(shakingTimeout);
});
</script>

<style scoped>
@import '../assets/animations.css';

.magic-ball-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  height: 100%;
  padding: 20px;
}

.magic-ball {
  width: 380px;
  height: 380px;
  background-color: #000;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  cursor: pointer;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
  transition: transform 0.2s ease;
}

.magic-ball:hover {
  transform: scale(1.02);
}

.magic-ball:active {
  transform: scale(0.98);
}

.magic-ball.shaking {
  animation: shake 1.2s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
}

.black-circle {
  width: 220px;
  height: 220px;
  background-color: black;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 1;
}
</style>
