<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Default content, if nothing is passed</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: ['header', 'text', 'theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
.backdrop {
  top: 0;
  left: 0;
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

.modal .actions {
  text-align: center;
  height: auto;
  margin-top: 8%;
  margin-bottom: 3%;
}

.modal .actions a{
  color: #333;
  padding: 2%;
  border-radius: 4px;
  text-decoration: none;
  margin: 4%;
}

.modal.sale {
  background: crimson;
  color: white;
}

.modal.sale a {
  color: white;
  border: 1px solid #eee;
}
</style>