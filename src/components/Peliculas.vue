<template>
  <div class="general">
    <div class="center">
      <section id="content">
        <h2 class="subheader">Películas</h2>

        <div class="favorita" v-if="favorita">
          La pelicula marcada es:
          <h2>{{favorita.title}}</h2>
        </div>

        <div class="misDatos" v-if="misDatos">
          <p v-html="misDatos"></p>
          <br>
          {{web | mayusculas | concatYear}}
        </div>

        <!--Listado articulos-->
        <div id="articles">
          <div v-for="pelicula in peliculasMayusculas" v-bind:key="pelicula.title">
            <Pelicula 
              :pelicula="pelicula"
              @favorita="haLlegadoLaPeliculaFavorita">
            </Pelicula>
          </div>
        </div>
      </section>
      <Sidebar></Sidebar>
      <div class="clearfix"></div>
    </div>
  </div>
</template>

<script>
import Pelicula from "./Pelicula";
import Sidebar from "./Sidebar";
export default {
  name: "Peliculas",
  components: {
    Pelicula,
    Sidebar,
  },
  methods:{
    haLlegadoLaPeliculaFavorita(favorita){
      this.favorita = favorita;
      // console.log(favorita);
      // alert("Se ha ejecutado el evento en el padre");
    }
  },
  filters:{
    mayusculas(value){
      return value.toUpperCase();
    },
    concatYear(value){
      let date = new Date();
      return value + ' ' + date.getFullYear();
    }
  },
  computed:{
    peliculasMayusculas(){
      let peliculasMod = this.peliculas;
      for (let i = 0; i < peliculasMod.length; i++) {
        peliculasMod[i].title = peliculasMod[i].title.toUpperCase();
      }
      return peliculasMod;
    },
    misDatos(){
      return 'Mi nombre es : ' + this.nombre + ' ' + this.apellidos + ' <br/>'
        + '<strong>Mi sitio web: </strong>' + this.web;
    }
  },
  data() {
    return {
      nombre: 'Leonardo Miguel',
      apellidos: 'Guilarte Carreño',
      web: 'LeonardoGuilarte.com',
      favorita:null,
      peliculas: [
        {
          title: "La La Land",
          year: 2016,
          image:
            "https://steemitimages.com/DQmPYvNqrTmwun5NfLP1WYe17T7WpQVcVTco8eb7J8K4Fbm/maxresdefault.jpg",
        },
        {
          title: "El señor de los anillos: El retorno del rey",
          year: 2003,
          image:
            "https://sites.google.com/site/portafolio2013boris/_/rsrc/1468866064027/3-el-senor-de-los-anillos-el-retorno-del-rey/dadad.jpg?height=400&width=400",
        },
        {
          title: "Avengers: Endgame",
          year: 2019,
          image:
            "https://upload.wikimedia.org/wikipedia/en/0/0d/Avengers_Endgame_poster.jpg",
        },
      ],
    };
  },
};
</script>
