<template>
  <BaseCard>
    <h2>{{ name }}</h2>
    <p>{{ club }}</p>
    <p>{{ price }} mln €</p>
    <div class="card-buttons">
      <a :href="profile"><BaseButton>SEE PROFILE</BaseButton></a>
      <BaseButton @click="removeTarget">REMOVE</BaseButton>
    </div>
  </BaseCard>
</template>

<script>
import BaseCard from './BaseCard.vue';
import BaseButton from './BaseButton.vue';

export default {
  props: ['name', 'club', 'price', 'profile'],
  components: {
    BaseCard,
    BaseButton,
  },
  methods: {
    removeTarget() {
      this.$emit('remove-target');
    },
  },
};
</script> 