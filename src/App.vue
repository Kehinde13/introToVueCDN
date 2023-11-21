<script setup>
 import Navbar from './components/Navbar.vue'
 import Modal from './components/Modal.vue'
</script>

<template>
  <!-- passing props with data binding -->
  <Navbar :theme="dark" />
  <button @click="toggelModal">Open Modal</button>
  <!-- @close recieves the emitted event -->
  <Modal :modal="showModal" @close="toggelModal">
    <p>How to use slot to pass props from parent to child component</p>
    <!-- How to use slot to outside of the slot block -->
    <template v-slot:headers>
        <h1>using named slot</h1>
    </template>
  </Modal>
</template>

<script>
 export default {
  name: 'app',
  data() {
   return {
    title: 'First vue app',
    showModal: false,
   }
 },
 methods: {
    toggelModal(){
      this.showModal = !this.showModal
    }
  }
 
}
</script>

<style scoped>

</style>
