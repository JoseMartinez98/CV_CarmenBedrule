<script setup>
import { onMounted, onBeforeUnmount, ref } from "vue";

const isScrolled = ref(false);
const isMenuOpen = ref(false);

function scrollTo(id, event) {
  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
  setTimeout(() => {
    event?.target?.blur();
  }, 100);

  // cerrar el menú hamburguesa al hacer click
  isMenuOpen.value = false;
}

function handleScroll() {
  isScrolled.value = window.scrollY > 50;
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <nav :class="['menu-fijo', { 'fondo-solido': isScrolled }]">
    <button
      class="hamburger"
      :class="{ open: isMenuOpen }"
      @click="isMenuOpen = !isMenuOpen"
      aria-label="Toggle menu"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <ul :class="{ open: isMenuOpen }">
      <li>
        <a href="#section1" @click.prevent="(e) => scrollTo('section1', e)">Inicio</a>
      </li>
      <li>
        <a href="#section2" @click.prevent="(e) => scrollTo('section2', e)">Sobre mí</a>
      </li>
      <li>
        <a href="#section3" @click.prevent="(e) => scrollTo('section3', e)">Proyectos</a>
      </li>
      <li>
        <a href="#section4" @click.prevent="(e) => scrollTo('section4', e)">Formación</a>
      </li>
      <li>
        <a href="#section5" @click.prevent="(e) => scrollTo('section5', e)">Contáctame</a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.menu-fijo {
  position: fixed;
  top: 0;
  left: 75%;
  transform: translateX(-50%);
  width: 600px;
  background: rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  box-shadow: none;
  padding: 10px;
  z-index: 1000;
  border-bottom: 2px solid #03055e;
  border-radius: 10px;
  transition: background 0.3s ease-in-out;
}

.menu-fijo ul {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin: 0 auto;
  padding: 0;
}

.menu-fijo li {
  margin: 0;
  transition: 0.2s;
}
.menu-fijo li:hover {
  color: #03045e;
  transform: scale(1.1);
  transition: transform 0.2s ease, color 0.2s ease;
}

.menu-fijo a {
  color: #03055e;
  text-decoration: none;
}

.menu-fijo a:hover {
  color: #fc4b08;
}

.fondo-solido {
  background: rgba(144, 224, 239, 0.5);
  backdrop-filter: blur(12px);
  border-radius: 10px;
}

.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1100;
}
.hamburger span {
  display: block;
  height: 3px;
  width: 100%;
  background: #03055e;
  border-radius: 2px;
  transition: all 0.3s ease;
}
.hamburger.open span:nth-child(1) {
  transform: rotate(45deg) translateY(8px);
}
.hamburger.open span:nth-child(2) {
  opacity: 0;
}
.hamburger.open span:nth-child(3) {
  transform: rotate(-45deg) translateY(-8px);
}
@media (max-width: 1070px) {
.menu-fijo{
  left: 50%;
}
}
@media (max-width: 768px) {
  .menu-fijo {
    width: 100%;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 20px;
  }

  .hamburger {
    display: flex;
  }

  .menu-fijo ul {
    position: absolute;
    top: 50px;
    left: 24px;
    flex-direction: column;
    background: rgba(255, 255, 255, 0.95);
    width: 100%;
    gap: 1rem;
    padding: 20px 0;
    display: none;
    border-bottom: 2px solid #03055e;
  }

  .menu-fijo ul.open {
    display: flex;
  }
}
</style>
