<template>
  <TheHeading></TheHeading>
  <TransferList></TransferList>
</template>

<script>
import TheHeading from './components/TheHeading.vue';
import TransferList from './components/TransferList.vue';

export default {
  components: {
    TheHeading,
    TransferList,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Roboto, Arial, sans-serif;
}
</style>