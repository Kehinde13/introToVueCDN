// eslint-disable-next-line vue/multi-word-component-names


<template>
   <!-- @click.self to make sure the function runs only when the div is specifically clicked -->
   <!-- there is @alt and @shift methods also -->
  <div v-if="modal" class="backdrop" @click.self="closeModal">
    <div class="modal">
       <!--  how to use ref to reference an element -->
        <h1 ref="hello">
        Hello World
    </h1>
    <button @click="logHeader">
        log header
    </button>
    <!-- render slot -->
    <slot></slot>
    <!-- render slot outside of the slot block -->
    <div>
      <slot name="headers"></slot>
    </div>
    
    </div>
  </div>
</template>

<script>
    export default {
      methods: {
      logHeader(){
        //refs to get the element from refs
        console.log(this.$refs.hello);
      },
      closeModal(){
        /* how to emit a function from a child component to the parent */
        this.$emit('close')
      }
    },
    /* how to accept theme from parent conponents */
    props: ['para', 'modal']
}
</script>

<style>
   .backdrop {
     top: 0;
     position: fixed;
     background: rgba(0,0,0,0.5);
     width: 100%;
     height: 100%;
   }

   .modal {
    width: 30%;
    margin: 50px auto;
    background: white;
    padding: 20px;
    text-align: center;
   }
</style>