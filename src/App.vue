<template>
  <h1>{{ title }}</h1>

  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @closeModal="setShowModal"/>
  </div>

  <button @click="setShowModal">Show modal</button>
  
  <!-- <input type="text" ref="name"/>
 <button @click="handleClick" >Click here</button> -->
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "My first App(Hello world)",
      header:"I am from the parent",
      text:"I am the description from the parent",
      showModal:false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus()
    },
    setShowModal(){
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

.active {
  background-color: red;
}

h1 {
  color: green;
}

button{
background:greenyellow;
}
</style>
