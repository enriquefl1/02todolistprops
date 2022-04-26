<template>
  <div class="lista">
    <ul>
      <li v-for="(nodo, i) in nodoTarea" :key="i">
        {{ nodo }}
        <input type="button" v-on:click="eliminarTarea(i)" value="Eliminar" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ListaTareas",
  props: {
    nodoTarea: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    eliminarTarea(i) {
      this.$emit("eliminarTarea", i);
    },
  },
};
</script>
