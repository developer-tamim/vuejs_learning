<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <h1>{{ name }}</h1>
  <h1>{{ number }}</h1>

  <button @click="number++">Increase me</button>
  <button @click="number--">Decrease me</button>
<button @click.shift="toggleModal">Show Modal</button>

<div v-if="showmodal">
  <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
  <Modal theme="" @close="toggleModal">
    <template v-slot:link>
      <div>
        <a href="#">Sign Up</a>
        <br>
        <a href="#">Sign In</a>
      </div>
    </template>
    <h1>This is called Slot</h1>
    <p>this is just a test of the slot</p>
  </Modal>
</div>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  
  data(){
    return {
      title: 'This is just a test :)',
      name: 'This is just a name :)',
      number:9999999993,
      header: 'Sign up for Giveaway',
      text: 'Grab your text',
      showmodal: false,
    }
  },

  methods: {
    toggleModal(){
      this.showmodal =!this.showmodal
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
