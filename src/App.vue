<template>
  <h1>{{ title }}</h1>

  <Modal header="I am from the parent" text="I am the description from the parent" />
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
      title: "My first App(Hello world)"
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus()
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
</style>
