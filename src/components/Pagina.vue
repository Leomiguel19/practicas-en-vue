<template>
  <div class="general">
    <Slider></Slider>
    <div class="center">
      <section id="content">
        <h2 class="subheader">Página de pruebas</h2>
        <h3>{{ id_desde_url }}</h3>
        <button @click="redirigirAlBlog()">Ir al blog</button>
      </section>
      <Sidebar></Sidebar>
      <div class="clearfix"></div>
    </div>
  </div>
</template>

<script>
import Slider from "./Slider.vue";
import Sidebar from "./Sidebar";
export default {
  name: "Pagina",
  components: {
    Slider,
    Sidebar,
  },
  mounted() {
    this.id_desde_url = this.$route.params.id;
  },
  data() {
    return {
      id_desde_url: null,
    };
  },
  methods: {
    actualizarNombre() {
      this.nombre = "Leonardo Guilarte";
    },
    redirigirAlBlog() {
      this.$router.push("Blog");
    },
  },
};
</script>
