<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">sprawdzamy ref</button>
  
  <div v-if="showModal">
    <Modal theme="on" @close="toggleModal">
      <template v-slot:links>
        <a href="#">omen</a>
        <a href="#">omen2</a>
      </template>
      <h1>jestem tu nowy</h1>
      <p>pokaż cycki</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template @click="toggleModalTwo"></template>
      <h1>jestem tu drugi raz</h1>
      <p>to jest drugi raz!!</p>
    </Modal>
  </div>

  <button @click="toggleModal">pokaż modal</button>
  <button @click="toggleModalTwo">pokaż drugi podal</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "MOJA PIERWSZA STYLÓWKA VUE",
      showModal: false,
      showModalTwo: false,
    };
  },

  methods: {
    handleClick() {
      this.$refs.name.classList.toggle("active");
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
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
  background: red;
}
</style>
