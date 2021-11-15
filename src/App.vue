<template>
  <h1>{{ title }}</h1>
  <p>Welcome !</p>

  <Modal v-if="showModal" theme="sale" @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign up</a>
      <a href="#">Register</a>
    </template>
    <h1>My first Vue app !</h1>
    <p>I'm training right here :)</p>
  </Modal>

  <Modal v-if="showModalTwo" @close="toggleModalTwo">
    <h1>Hi, i'm the second modal !</h1>
    <p>I'm not as cool at the first, but np</p>
  </Modal>

  <button @click="toggleModal">Open modal</button>
  <button @click="toggleModalTwo">Open modal two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first Vue app !',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.test)
      let h1 = this.$refs.test
      h1.style.color = 'red'
      h1.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid rgb(194, 194, 194);
  display: inline-block;
  padding-bottom: 10px;
}
</style>
