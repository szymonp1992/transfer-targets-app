<template>
  <div class="tab-switcher__list">
    <BaseButton @click="openTargetsTab">Transfer targets</BaseButton>
    <BaseButton @click="openAddTargetTab">Add new target</BaseButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  components: {
    BaseButton,
  },
  methods: {
    openTargetsTab() {
      this.$emit('open-targets-tab');
    },
    openAddTargetTab() {
      this.$emit('open-add-target-tab');
    },
  },
};
</script>

<style scoped>
.tab-switcher__list {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  gap: 20px;
}

/* .tab-switcher__list li button {
  background: #30346d;
  color: white;
  text-transform: uppercase;
  padding: 20px;
  border-radius: 25px;
  box-shadow: 4px 4px 2px #888888;
} */
</style>