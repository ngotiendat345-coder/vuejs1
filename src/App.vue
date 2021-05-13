<template>
  <div>
    <h1>{{ title }}</h1>
    <teleport to="#modals" v-if="showModal">
      <Modal theme='sale' @close="toggleModal">
        <template v-slot:links>
           <a href="#">sign up now</a>
        <a href="#">more info</a>
        </template>
        <h1>{{heading}}</h1>
        <p>{{text}}</p>
      </Modal>
    </teleport>
    <button @click="toggleModal">Toggle modal</button>
  </div>
</template>

<script>
import Modal from './components/Modal'
export default {
  name: 'App',
  components: { Modal },
  data () {
    return {
      title: 'My First Vue App!',
      heading: 'Sign up for the Givaway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false
    }
  },
  methods: {
    toggleModal () {
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
