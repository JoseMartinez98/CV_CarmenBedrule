<script setup>
import { ref } from "vue";

const flippedIndex = ref(null);

const toggleFlip = (index) => {
  flippedIndex.value = flippedIndex.value === index ? null : index;
};
</script>

<template>
  <div class="container">
    <div class="sobreMi">
      <div class="textoInfo">
        <h2>Un poco sobre mí:</h2>
        <p>
          Profesional <span class="naranja">versátil y detallista</span>, con
          experiencia en el ámbito
          <span class="naranja">cultural, comercial y diseño</span>.
          <br /><br />

          Actualmente estoy haciendo un curso de
          <span class="naranja">diseño de productos gráficos</span>.<br /><br />

          En mi último trabajo de
          <span class="naranja">promotora cultural</span>, destaqué por mi
          <span class="naranja">capacidad de adaptación</span> ante cambios e
          imprevistos, manteniendo una
          <span class="naranja">actitud positiva</span>.<br /><br />
          En mi <span class="naranja">experiencia en ventas</span>, participé
          activamente en todo el
          <span class="naranja">proceso creativo y operativo</span>: desde la
          producción en imprenta, hasta el empaquetado, como en el diseño de
          material publicitario para redes sociales y la venta directa de
          productos. Fui reconocida por mi
          <span class="naranja">iniciativa y participación</span> constante en
          nuevos proyectos.<br /><br />

          Fuera del ámbito laboral, me apasiona el deporte, llevar un estilo de
          vida saludable y disfrutar de una buena lectura en mi tiempo libre.
        </p>
      </div>
      <div class="idiomas">
        <h2>Idiomas:</h2>
        <div class="lengua">
          <div class="idioma">
            <img src="/images/idiomas/spain.png" alt="Bandera de España" />
            <p>Español: Nativo</p>
          </div>
          <div class="idioma">
            <img src="/images/idiomas/romain.png" alt="Bandera de Rumanía" />
            <p>Rumano: Nativo</p>
          </div>
          <div class="idioma">
            <img
              src="/images/idiomas/english.png"
              alt="Bandera de Reino Unido"
            />
            <p>Inglés: B1</p>
          </div>
        </div>
      </div>
    </div>
    <h2>Mis herramientas:</h2>
    <div class="herramientas">
      <div
        v-for="(item, index) in [
          {
            img: '/images/herramientas/adobe.png',
            title: 'Adobe Illustrator',
            back: 'Programa para diseño vectorial',
          },
          {
            img: '/images/herramientas/photoshop.png',
            title: 'Photoshop',
            back: 'Programa para edición de foto',
          },
          {
            img: '/images/herramientas/Clipchamp.png',
            title: 'Clipchamp',
            back: 'Editor de video online',
          },
          {
            img: '/images/herramientas/excell.webp',
            title: 'Excel',
            back: 'Hojas de cálculo avanzadas',
          },
          {
            img: '/images/herramientas/shopify.png',
            title: 'Shopify',
            back: 'APP de e-commerce',
          },
          {
            img: '/images/herramientas/saga.png',
            title: 'Saga',
            back: 'Gestión de proyectos',
          },
          {
            img: '/images/herramientas/playoff.png',
            title: 'Playoff',
            back: 'Planificación estratégica',
          },
          {
            img: '/images/herramientas/Smartbill.jpeg',
            title: 'Smartbill',
            back: 'Facturación inteligente',
          },
          {
            img: '/images/herramientas/wordpress.png',
            title: 'WordPress',
            back: 'Gestor de contenidos',
          },
        ]"
        :key="index"
        class="iconos"
        :class="{ flipped: flippedIndex === index }"
        @click="toggleFlip(index)"
      >
        <div class="inner">
          <div class="front">
            <img :src="item.img" :title="item.title" />
            <p>{{ item.title }}</p>
          </div>
          <div class="back">
            <p>{{ item.back }}</p>
          </div>
        </div>
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
  flex-direction: column;
  align-items: center;
}
h2 {
  font-size: 40px;
  margin: 0;
  line-height: 40px;
  color: #03045e;
  text-shadow: 2px 2px 2px #023e8a;
  margin-bottom: 20px;
}
.sobreMi {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 40px;
}
.textoInfo {
  max-width: 60%;
  font-size: 20px;
  color: #03045e;
  font-weight: bold;
  margin-bottom: 80px;
}
.naranja {
  color: #fc4b08;
}
.idiomas {
  max-width: 20%;
  margin: 0 auto;
  text-align: center;
}
.lengua {
  display: flex;
  justify-content: center;
  flex-direction: column;
  gap: 1rem;
  margin-top: 20px;
}
.idioma {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.idioma img {
  width: 60px;
  height: auto;
}
.idioma p {
  margin-top: 8px;
  font-weight: bold;
  color: #03045e;
}
.herramientas {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  margin: 0 auto;
  max-width: 100%;
}
.iconos {
  perspective: 1000px;
  margin: 20px;
  min-width: 320px;
  min-height: 120px;
  cursor: pointer;
}
.inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}
.iconos.flipped .inner {
  transform: rotateY(180deg);
}
.front,
.back {
  position: absolute;
  width: 100%;
  height: 100%;
  border: 1px solid #03045e;
  border-radius: 10px;
  display: flex;
  gap: 10px;
  justify-content: center;
  align-items: center;
  backface-visibility: hidden;
  background-color: #0076b6a0;
  font-size: 25px;
  font-weight: bold;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.front img {
  width: 60px;
  max-height: 60px;
}
.front p,
.back p {
  margin: 0;
  padding: 8px;
  text-align: center;
  word-break: break-word;
}

.back {
  transform: rotateY(180deg);
  color: #03045e;
  border: 1px solid #fc4b08;
  background-color: #fb683280;
}

@media (max-width: 760px) {
  .container {
    min-width: 95%;
  }
  .sobreMi {
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 20px;
  }

  .textoInfo {
    max-width: 100%;
    font-size: 16px;
    margin-bottom: 40px;
    text-align: justify;
  }

  .idiomas {
    max-width: 100%;
  }

  .lengua {
    flex-direction: row;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }

  h2 {
    margin-top: 80px;
    font-size: 28px;
    line-height: 32px;
  }

  .idioma img {
    width: 45px;
  }

  .idioma p {
    font-size: 14px;
  }

  .iconos {
    min-width: 200px;
    min-height: 100px;
    margin: 10px;
  }

  .herramientas {
    min-width: auto;
    max-width: 100%;
    min-height: 120px;
    justify-content: center;
    gap: 0.5rem;
  }

  .iconos {
    flex: 1 1 calc(50% - 20px);
    max-width: 120px;
    min-height: 90px;
    margin: 0.5;
  }

  .front,
  .back {
    display: flex;
    font-size: 16px;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 6px;
  }

  .front img {
    width: 40px;
    height: auto;
  }
}
</style>
