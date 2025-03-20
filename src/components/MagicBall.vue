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

<script>
import AnswerCircle from './AnswerCircle.vue';
import BallEffects from './BallEffects.vue';
import AnswerService from '../services/AnswerService';

export default {
  name: 'MagicBall',
  components: {
    AnswerCircle,
    BallEffects
  },
  data() {
    return {
      isShaking: false,
      showAnswer: false,
      showMysticLight: false,
      showBubbles: false,
      currentAnswer: '',
      shakingTimeout: null
    };
  },
  methods: {
    shakeBall() {
      if (this.isShaking) return;
      
      this.showAnswer = false;
      this.showMysticLight = false;
      
      this.isShaking = true;
      this.showBubbles = true;
      
      this.currentAnswer = AnswerService.getRandomAnswer();
      
      this.shakingTimeout = setTimeout(() => {
        this.isShaking = false;
        this.showBubbles = false;
        
        this.showMysticLight = true;
        this.showAnswer = true;
        
        setTimeout(() => {
          this.showMysticLight = false;
        }, 3000);
      }, 1200);
    }
  },
  beforeUnmount() {
    if (this.shakingTimeout) clearTimeout(this.shakingTimeout);
  }
};
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
