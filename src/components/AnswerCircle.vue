<template>
  <div class="answer-circle" :class="{ 'reveal': showAnswer }">
    <div class="bubbles-container" :class="{ 'active': showBubbles }">
      <div class="bubble bubble-1"></div>
      <div class="bubble bubble-2"></div>
      <div class="bubble bubble-3"></div>
      <div class="bubble bubble-4"></div>
      <div class="bubble bubble-5"></div>
      <div class="bubble bubble-6"></div>
    </div>
    <div class="answer-text" v-if="showAnswer">
      <span v-for="(word, wordIndex) in answerWords" :key="wordIndex" 
            :style="{ animationDelay: wordIndex * 0.1 + 's' }"
            class="word-reveal">
        {{ word }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AnswerCircle',
  props: {
    showAnswer: {
      type: Boolean,
      default: false
    },
    answerText: {
      type: String,
      default: ''
    },
    showBubbles: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    answerWords() {
      console.log('answerText:', this.answerText);
      console.log('showAnswer:', this.showAnswer);
      return this.answerText ? this.answerText.split(' ') : [];
    }
  }
};
</script>

<style scoped>
@import '../assets/animations.css';

.answer-circle {
  width: 180px;
  height: 180px;
  background-color: #0c52a8;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: bold;
  text-align: center;
  font-size: 14px;
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5),
              inset 0 0 15px rgba(255, 255, 255, 0.1);
  transform: scale(1);
  opacity: 1;
  position: relative;
  overflow: hidden;
}

.answer-circle.reveal {
  transform: scale(1.05);
  box-shadow: 0 0 20px rgba(13, 110, 253, 0.7),
              inset 0 0 15px rgba(255, 255, 255, 0.3);
  background-color: #1a75ff;
}

.answer-text {
  padding: 16px;
  word-wrap: break-word;
  font-size: 18px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  position: relative;
  z-index: 2;
  opacity: 0;
  animation: answerAppear 0.3s forwards;
  max-width: 90%;
  gap: 4px;
}

.word-reveal {
  opacity: 0;
  animation: wordFadeIn 0.4s forwards;
  display: inline-block;
  margin-right: 2px;
  padding: 0 2px;
  line-height: 1.4;
}

/* Стили для пузырьков */
.bubbles-container {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 50%;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease;
  pointer-events: none;
  z-index: 1;
}

.bubbles-container.active {
  opacity: 1;
  visibility: visible;
}

.bubble {
  position: absolute;
  background: rgba(255, 255, 255, 0.4);
  border-radius: 50%;
  opacity: 0;
  bottom: 0;
}

.bubble-1 {
  width: 20px;
  height: 20px;
  left: 20%;
  animation: bubble-rise 1.8s ease-in-out infinite;
  animation-delay: 0.2s;
}

.bubble-2 {
  width: 14px;
  height: 14px;
  left: 35%;
  animation: bubble-rise 1.4s ease-in-out infinite;
  animation-delay: 0.6s;
}

.bubble-3 {
  width: 18px;
  height: 18px;
  left: 50%;
  animation: bubble-rise 2s ease-in-out infinite;
  animation-delay: 0.1s;
}

.bubble-4 {
  width: 12px;
  height: 12px;
  left: 65%;
  animation: bubble-rise 1.6s ease-in-out infinite;
  animation-delay: 0.4s;
}

.bubble-5 {
  width: 22px;
  height: 22px;
  left: 75%;
  animation: bubble-rise 1.9s ease-in-out infinite;
  animation-delay: 0.8s;
}

.bubble-6 {
  width: 16px;
  height: 16px;
  left: 40%;
  animation: bubble-rise 1.7s ease-in-out infinite;
  animation-delay: 0.5s;
}

@keyframes answerAppear {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes wordFadeIn {
  0% { opacity: 0; transform: translateY(8px); }
  100% { opacity: 1; transform: translateY(0); }
}
</style>
