<template>
  <h1>{{ title }}</h1>
 
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
  </div>
  <button @click="toggleModal">Click Me</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components:{ Modal },
  data(){
    return{
      title: 'Welcome!',
      header: 'Best Burger in Town',
      text: 'Finger Licking Good',
      showModal: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
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
h1{
  color: blueviolet;

}
</style>
