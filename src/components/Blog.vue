<template>
  <div class="general">
    <Slider texto="Bienvenidos a mi primer página con vue JS">
    </Slider>
    <div class="center">
      <section id="content">
        <h2 class="subheader">Blog</h2>
      </section>
      <Sidebar></Sidebar>
      <div class="clearfix"></div>
    </div>
  </div>
</template>

<script>
import Slider from "./Slider";
import Sidebar from "./Sidebar";
export default {
  name: "Blog",
  components: {
    Slider,
    Sidebar,
  },
};
</script>
