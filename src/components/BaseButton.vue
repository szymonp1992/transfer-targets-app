<template>
  <button>
    <slot></slot>
  </button>
</template>

<style>
button {
  border: none;
  background: #30346d;
  color: white;
  text-transform: uppercase;
  padding: 20px;
  border-radius: 25px;
}

button:hover {
  cursor: pointer;
}
</style>