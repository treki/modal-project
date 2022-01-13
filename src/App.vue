<template>
  <h1>{{ title }}</h1>
    <h2>{{ header }}</h2>
    <div v-if="showModal">
      <Modal theme="blue" @close="toggleModal">
            <template v-slot:link>
              <a href="https://www.foxnews.com/">BLUE PILL</a>
            </template>
        <h1>You take the BLUE pill the story ends.</h1>
        <p>You wake up in your bed and believe whatever it is you want to believe!</p>
      </Modal>
    </div>

    <div v-if="showModalTwo">
      <Modal theme="" @close="toggleModalTwo">
        <h1>You take the RED pill you stay in Wonderland</h1>
        <p>And I show you how deep the rabbit hole goes</p>
        <template v-slot:link>
              <a href="https://footprint.wwf.org.uk/#/">RED PILL</a>
            </template>
      </Modal>
    </div>
  <button class="blue" @click="toggleModal">BLUE</button>
  <button class="red" @click="toggleModalTwo">RED</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components:{ Modal },
  data(){
    return{
      title: 'Life is all about choices, what\'s it gonna be?',
      header: 'Will you choose blue or red?',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
     toggleModalTwo(){
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

p{
  color: rgb(255, 253, 253);
}
</style>
