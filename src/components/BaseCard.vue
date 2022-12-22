<template>
  <div class="base-card">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style>
.base-card {
  color: black;
  padding: 20px;
  border-radius: 25px;
  box-shadow: 4px 4px 2px #888888;
  margin-top: 20px;
  width: 80%;
  background-color: #eeeeee;
  min-height: 100px;
}

.base-card h2,
.base-card div,
.base-card p {
  margin: 1rem;
}

.card-buttons {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  gap: 20px;
}
</style>