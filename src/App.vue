<template>
  <div id="app">
    <h1>{{ message }}</h1>
    <input type="text" v-model="valorTarea" />
    <input type="button" v-on:click="agregarTarea" value="Agregar" />

    <ListaTareas :nodoTarea="nodoTarea" @eliminarTarea="eliminarTarea" />
  </div>
</template>

<script>
import ListaTareas from "@/components/ListaTareas.vue";

export default {
  name: "App",
  components: {
    ListaTareas,
  },
  data() {
    return {
      message: "Ingrese una tarea en el campo de texto",
      valorTarea: "",
      nodoTarea: ["Comprar Pan", "Lavar los platos", "Lavar los vasos"],
    };
  },
  methods: {
    agregarTarea() {
      this.valorTarea === ""
        ? alert("No puedes dejar el campo valor vacio")
        : this.nodoTarea.push(this.valorTarea);
      this.valorTarea = "";
    },
    eliminarTarea(i) {
      this.nodoTarea.splice(i, 1);
    },
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

.lista {
  width: 290px;
  margin: 0 auto;
  text-align: left;
}
</style>
