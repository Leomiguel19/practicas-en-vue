<template>
  <div class="general">
    <Slider 
      texto="Bienvenidos a mi primer página con vue JS"
      home="true"
    >
    </Slider>
    <div class="center">
      <section id="content">
        <h2 class="subheader">Últimos artículos</h2>

        <!--Listado articulos-->
        <div id="articles">
          <article class="article-item" id="article-template">
            <div class="image-wrap">
              <img
                src="https://unhabitatmejor.leroymerlin.es/sites/default/files/styles/header_category/public/2018-10/4%20paisaje%20macedonia.jpg?itok=AELknmF8"
                alt="Paisaje"
              />
            </div>

            <h2>Articulo de prueba</h2>
            <span class="date">
              Hace 5 minutos
            </span>
            <a href="#">Leer más</a>

            <div class="clearfix"></div>
          </article>
        </div>
      </section>
      <Sidebar></Sidebar>
      <div class="clearfix"></div>
    </div>
  </div>
</template>

<script>
import Slider from './Slider.vue';
import Sidebar from './Sidebar';
export default {
  name: "LastArticles",
  components: {
    Slider,
    Sidebar,
  }
};
</script>
