<template>
  <div id="app">
    <img alt="to do list icono" src="./assets/list.png">
    <h1 class="fw-bold my-4 text-secondary"> Tareas por realizar</h1>
    <input v-model="tareas" class="mx-4" type="text">
    <button @click="agregarTarea()" class="btn btn-outline-info">Agregar</button>
    <HelloWorld :list="arregloTareas"/>
        
    <div class="d-grid gap-2 col-4 mx-auto" v-if="arregloTareas.length > 0">
      <button @click="limpiar()" class="btnlimpiar btn btn-danger fw-bold my-4">Limpiar</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      arregloTareas: [],
      tareas: ""
    }
  },
  components: {
    HelloWorld,
  },
  methods: {
    agregarTarea() {
      if(!this.tareas) return
      this.arregloTareas.push({tareas: this.tareas})
      this.tareas = ""
    },
    limpiar(){
      this.arregloTareas = []
    }
  },
};
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  h1 {
    font-family: 'Nanum Pen Script', cursive;
    font-size: 55px;
  }
  img {
    width: 20%;
  }
  button {
    height: 40px;
  }
  input {
    height: 40px;
    width: 300px;
  }
  .btnlimpiar {
    font-size: 20px;
  }

</style>
