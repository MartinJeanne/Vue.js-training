<template>
  <div class="backdrop">
    <div class="modal">
      <p>modal content</p>
    </div>
  </div>
</template>

<style>
.backdrop {
  top: 0;
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
}
.modal {
  width: 35vw;
  padding: 2.5vh;
  margin: 20vh auto;
  background-color: rgb(228, 228, 228);
  border-radius: 2vh;
}
</style>