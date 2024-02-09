<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <h1>{{ name }}</h1>
  <h1>{{ number }}</h1>

  <button @click="number++">Increase me</button>
  <button @click="number--">Decrease me</button>

<div v-if="showmodal">
  <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
</div>
<button @click.shift="toggleModal">Show Modal</button>

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
      number:25,
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
