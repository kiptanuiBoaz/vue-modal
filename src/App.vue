<template>
  <h1>{{ title }}</h1>

  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @closeModal="setShowModal">
      <template v-slot:links>
        <a href="#">More info</a>
        <a href="#">Sign Up</a>
      </template>
      <h1>This is the slot title</h1>
      <p>This si the slot description</p>
    </Modal>
  </teleport>


  <teleport to=".modals" v-if="showModalTwo">
    <Modal @closeModal="setShowModalTwo">
      <h1>Sign Up to the news letter</h1>
      <p>For updates and promocodes</p>
    </Modal>
  </teleport>
  <button @click="setShowModal">Show modal</button>
  <button @click="setShowModalTwo">Show modalTwo</button>

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
      header: "I am from the parent",
      text: "I am the description from the parent",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus()
    },
    setShowModal() {
      this.showModal = !this.showModal
    },
    setShowModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals {
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

button {
  background: greenyellow;
}
</style>
