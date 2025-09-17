<script setup>
import { ref, onMounted } from "vue";

const ocupaciones = ["Promotora cultural", "Diseñadora gráfica"];
const currentIndex = ref(0);

onMounted(() => {
  setInterval(() => {
    currentIndex.value = (currentIndex.value + 1) % ocupaciones.length;
  }, 3000);
});
</script>

<template>
  <div class="container">
    <div class="foto">
      <img src="/images/perfil.jpeg" />
      <div class="social-icons">
        <a
          href="https://www.linkedin.com/in/carmen-bedrule-b90a99375/?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app"
          target="_blank"
          title="LinkedIn"
        >
          <i class="fab fa-linkedin"></i>
        </a>
        <a href="tel:+34624091248" title="Llamar al móvil">
          <i class="fas fa-phone"></i>
        </a>
        <a href="mailto:carmen.bdr21@gmail.com" title="Enviar correo">
          <i class="fas fa-envelope"></i>
        </a>
      </div>
    </div>
    <div class="info">
      <h1>Carmen Bedrule</h1>
      <div class="ocupacion">
        <transition name="slide" mode="out-in">
          <h2 :key="currentIndex">{{ ocupaciones[currentIndex] }}</h2>
        </transition>
      </div>
      <div>
        <h3><span class="rosa">Hago realidad tus proyectos.</span></h3>
        <h3>
          Si tienes alguna<span class="rosa"> idea en mente</span> 
          que no sepas como <span class="rosa">diseñar</span>, 
          ponte en <span class="rosa"> contacto conmigo</span> y yo
          <span class="rosa">
            resolveré 
            tu problema.
          </span>
        </h3>
        <br />
        <a href="documents/CarmenBedruleCV.pdf" download class="boton-rosa"
          >⬇ Descargar CV</a
        >
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 80%;
  margin: 0 auto;
  margin-top: 80px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 10%;
}
h1 {
  font-size: 80px;
  position: relative;
  display: inline-block;
  text-shadow: 2px 2px 2px #03045e;
  margin-bottom: 0px;
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.6s ease, opacity 0.6s ease;
  position: absolute;
  width: 100%;
  will-change: transform, opacity;
}
.slide-enter-from {
  transform: translate3d(0, 100%, 0);
  opacity: 0;
}
.slide-enter-to {
  transform: translate3d(0, 0, 0);
  opacity: 1;
}
.slide-leave-from {
  transform: translate3d(0, 0, 0);
  opacity: 1;
}
.slide-leave-to {
  transform: translate3d(0, -100%, 0);
  opacity: 0;
}

.foto {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 10%;
}
.foto > img {
  height: 400px;
  width: 400px;
  border-radius: 600px;
  border: 2px solid #03045e;
}
.social-icons {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
  align-items: center;
  font-size: 3rem;
  gap: 40px;
}
.social-icons a {
  color: #03045e;
  text-decoration: none;
}
.social-icons a:hover {
  color: #fc4b08;
}
.ocupacion {
  padding: auto;
  position: relative;
  height: 60px;
  overflow: hidden;
}

h2 {
  font-size: 50px;
  margin: 5px;
  line-height: 40px;
  color: #03045e;
  text-shadow: 2px 2px 2px #023e8a;
}
.rosa {
  color: #0096c7;
}
h3 {
  color: #03045e;
  font-size: 25px;
}
.boton-rosa {
  display: inline-block;
  padding: 12px 24px;
  background: #03045e;
  color: white;
  font-size: 30px;
  font-weight: bold;
  border-radius: 30px;
  text-decoration: none;
  box-shadow: 0 4px 10px #8fd7ef;
  transition: all 0.3s ease;
}
.boton-rosa:hover {
  background: #fc4b08;
  box-shadow: 0 6px 14px #efbdab;
  transform: translateY(-2px);
}
.boton-rosa:active {
  transform: translateY(0);
  box-shadow: 0 3px 8px #0096c7;
}
@media (max-width: 1070px) {
h2 {
  font-size: 30px;
  margin: 5px;
  line-height: 40px;
  color: #03045e;
  text-shadow: 2px 2px 2px #023e8a;
}
}
@media (max-width: 760px) {
  .container {
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 40px;
  }

  .foto > img {
    width: 250px;
    height: 250px;
  }

  h1 {
    font-size: 40px;
  }

  h2 {
    font-size: auto;
    line-height: 34px;
    margin: auto;
  }

  h3 {
    font-size: 18px;
    line-height: 26px;
  }

  .boton-rosa {
    font-size: 20px;
    padding: 10px 20px;
  }

  .social-icons {
    font-size: 2rem;
    gap: 25px;
  }
}
</style>
