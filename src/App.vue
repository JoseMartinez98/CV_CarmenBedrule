<script setup>
import { onMounted, ref } from "vue";
import Menu from "./components/Menu.vue";
import Encabezado from "./components/Encabezado.vue";
import SobreMi from "./components/SobreMi.vue";
import PieDePagina from "./components/PieDePagina.vue";
import Formacion from "./components/Formacion.vue";
import Formulario from "./components/Formulario.vue";
import Proyectos from "./components/Proyectos.vue";

// Refs para las secciones
const sections = ref([]);

onMounted(() => {
  sections.value = document.querySelectorAll(".secciones");

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("in-view");
          observer.unobserve(entry.target); // Solo animar una vez
        }
      });
    },
    { threshold: 0.1 } // 10% visible para activar
  );

  sections.value.forEach((section) => {
    section.classList.add("before-view");
    observer.observe(section);
  });
});
</script>

<template>
  <div class="container">
    <div class="bubbles">
      <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div>
      <Menu />
    </div>

    <div id="section1" class="secciones">
      <Encabezado />
    </div>

    <div id="section2" class="secciones">
      <SobreMi />
    </div>

    <div id="section3" class="secciones">
      <Proyectos />
    </div>

    <div id="section4" class="secciones">
      <Formacion />
    </div>

    <div id="section5" class="secciones">
      <Formulario />
    </div>

    <div class="pie">
      <PieDePagina />
    </div>
  </div>
</template>

<style scoped>
.secciones {
  margin-top: 200px;
  scroll-margin-top: 120px; 
}
.pie{
  margin-top: 100px;
}

.before-view {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.8s ease;
}

.in-view {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 760px) {
  .secciones {
    margin-top: 100px;
    scroll-margin-top: 80px;
  }
}
</style>
