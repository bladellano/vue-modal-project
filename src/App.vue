<template>
  <h1>{{title}}</h1>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus, quisquam.</p>
  <div v-if="showModal">
    <!-- <Modal
    :header="header"
    :text="text"
    theme="sale"
    @close="toggleModal"
    /> -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
          <a href="#">sign up now</a>          
          <a href="#">more info</a>          
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab yout ninja sawg for falf price</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Open Modal (alt)</button>
  <input type="text" ref="name">
  <button @click="handleClick" >Click me</button>
</template>

<script>

import Modal from './components/Modal'

export default {
  name: "App",
  components: {Modal},
  data(){
    return {
      title: 'Meu primeiro app vie data vue',
      header:'Sign up for the Giveaway!',
      text:'Grab you ninja sawf for half price!',
      showModal:false
    }
  },
  methods:{
    handleClick(){
      alert('Hello');
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()

    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  }
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
  color: brown;
}
</style>
