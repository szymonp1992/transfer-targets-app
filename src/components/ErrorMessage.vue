<template>
  <div class="error-container">
    <h2>Not a valid transfer target</h2>
    <p>
      Some of the parameters are missing. Enter all parameters and try again
    </p>
    <BaseButton @click="closeError">Close</BaseButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  components: {
    BaseButton,
  },
  methods: {
    closeError() {
      this.$emit('close-error-modal');
    },
  },
};
</script>

<style scoped>
.error-container {
  position: absolute;
  top: 20%;
  left: 20%;
  height: 60%;
  width: 60%;
  color: white;
  border: 10px solid #bc0572;
  background-color: #bc0572be;
  backdrop-filter: blur(5px);
  border-radius: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 2rem;
  padding: 2rem;
}

.error-container * {
  text-align: center;
}

.error-container button {
  background-color: #3a0123;
}
</style>