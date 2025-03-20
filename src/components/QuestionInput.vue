<template>
  <div class="question-input">
    <input 
      type="text" 
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      placeholder="Задайте вопрос и нажмите на шар..."
      :disabled="disabled"
    />
  </div>
</template>

<script>
export default {
  name: 'QuestionInput',
  props: {
    modelValue: {
      type: String,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
.question-input {
  margin-top: 20px;
  width: 100%;
  max-width: 400px;
}

.question-input input {
  width: 100%;
  padding: 10px;
  border-radius: 20px;
  border: 1px solid #ccc;
  font-size: 16px;
  text-align: center;
  transition: all 0.3s ease;
}

.question-input input:focus {
  outline: none;
  border-color: #1a75ff;
  box-shadow: 0 0 10px rgba(30, 144, 255, 0.3);
}
</style>
