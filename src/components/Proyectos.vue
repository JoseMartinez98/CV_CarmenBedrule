<script setup></script>
<template>
  <div class="container">
    <h2>Algunos de mis proyectos:</h2>
    <div class="proyectos">
      <div class="tarjetaProyecto">
        <div class="slider">
          <div class="slides">
            <img src="/images/proyectos/portada1.png" />
            <img src="/images/proyectos/proyecto1_pagina2.png" />
            <img src="/images/proyectos/proyecto1_pagina3.png" />
          </div>
        </div>
        <div class="descripcionProyecto">
          <div class="tools">
            <img src="/images/herramientas/adobe.png" />
            <img src="/images/herramientas/photoshop.png" />
            <a
              href="/documents/proyectos/fitnessDiariesCarmenBedrule.pdf"
              download
              class="btnDescargar"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 16v2a2 2 0 002 2h12a2 2 0 
                         002-2v-2M7 10l5 5m0 0l5-5m-5 5V4"
                />
              </svg>
            </a>
          </div>
          <p>
            Revista Fitness Diaries: Fue uno de mis últimos proyectos en el curso de AI enfocado al mundo
            del deporte y la salud.
          </p>
        </div>
      </div>

      <div class="tarjetaProyecto">
        <div class="slider">
          <div class="slides">
            <img src="/images/proyectos/portofolio.png" />
            <img src="/images/proyectos/proyecto3_pagina2.png" />
            <img src="/images/proyectos/proyecto3_pagina3.png" />
          </div>
        </div>
        <div class="descripcionProyecto">
          <div class="tools">
            <img src="/images/herramientas/adobe.png" />
            <img src="/images/herramientas/photoshop.png" />
            <a
              href="/documents/proyectos/ejemploPortafolio.pdf"
              download
              class="btnDescargar"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 16v2a2 2 0 002 2h12a2 2 0 
                         002-2v-2M7 10l5 5m0 0l5-5m-5 5V4"
                />
              </svg>
            </a>
          </div>
          <p>
            Trabajo Portfolio: Este es uno de los ejemplos en los que estuve
            trabajando en el curso de AI.
          </p>
        </div>
      </div>

      <div class="tarjetaProyecto">
        <img src="/images/proyectos/portada3.png" />
        <div class="descripcionProyecto">
          <div class="tools">
            <img src="/images/herramientas/adobe.png" />
            <img src="/images/herramientas/Clipchamp.png" />
            <img src="/images/herramientas/wordpress.png" />
            <a
              href="/documents/proyectos/rutaTeatralizada.pdf"
              download
              class="btnDescargar"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 16v2a2 2 0 002 2h12a2 2 0 
                         002-2v-2M7 10l5 5m0 0l5-5m-5 5V4"
                />
              </svg>
            </a>
          </div>
          <p>
            Ruta teatralizada: “Sueños de ida y vuelta”.
            es una ruta teatralizada en Benitagla que rinde homenaje a la
            memoria de la emigración y al patrimonio cultural del pueblo. A
            través de escenas vividas en sus calles, los espectadores recorren
            historias y tradiciones, reflexionando sobre las raíces y el regreso
            a la tierra de origen.
            <a href="https://www.youtube.com/watch?v=dftuDl1iZqk">Vídeo_1</a>
            <a href="https://www.youtube.com/watch?v=xyxdi2aPCLA">Video_2</a>
            <a href="https://descubrefilabresalhamilla.wordpress.com/">Web</a>
          </p>
        </div>
      </div>

      <div class="tarjetaProyecto">
        <img src="/images/proyectos/portada4.png" />
        <div class="descripcionProyecto">
          <div class="tools">
            <img src="/images/herramientas/adobe.png" />
            <a
              href="/documents/proyectos/rutaSelfieEnLasSierrasDeLosFilabres.pdf"
              download
              class="btnDescargar"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 16v2a2 2 0 002 2h12a2 2 0 
                         002-2v-2M7 10l5 5m0 0l5-5m-5 5V4"
                />
              </svg>
            </a>
          </div>
          <p>
            Ruta selfie en la comarca de los Filabres: Un proyecto innovador que
            combina patrimonio y cultura digital para redescubrir los paisajes,
            oficios y arquitecturas de diez municipios del interior de Almería.
            A través de recorridos fotográficos, se fomenta un turismo
            sostenible que conecta la belleza del territorio con la
            participación activa de sus visitantes.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 95%;
  margin: 0 auto;
  margin-top: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
h2 {
  font-size: 30px;
  margin: 0;
  line-height: 40px;
  color: #03045e;
  text-shadow: 2px 2px 2px #023e8a;
  margin-bottom: 20px;
}
.proyectos {
  max-width: 90%;
  display: flex;
  flex-wrap: wrap;
  margin: 2rem;
  gap: 2rem;
  align-items: center;
  justify-content: center;
}
.tarjetaProyecto {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 500px;
  min-height: 500px;
  background-color: white;
  border: 1px solid #03045e;
  box-shadow: 0 0 15px #023e8a;
}
.tarjetaProyecto > img {
  width: 95%;
  height: 300px;
  margin: 1rem;
}

.slider {
  width: 95%;
  height: 320px;
  margin: 1rem;
  position: relative;
  overflow: hidden;
}

.slides {
  position: relative;
  width: 100%;
  height: 100%;
}

.slides img {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0;
  animation: fade 12s infinite;
}
.tarjetaProyecto:nth-child(1) .slides img {
  object-fit: contain;
  background: #fff; /* blanco */
}

.tarjetaProyecto:nth-child(2) .slides img {
  object-fit: contain;
  background: #000; /* negro */
}

.slides img:nth-child(1) {
  animation-delay: 0s;
}
.slides img:nth-child(2) {
  animation-delay: 4s;
}
.slides img:nth-child(3) {
  animation-delay: 8s;
}

@keyframes fade {
  0% {
    opacity: 0;
  }
  5% {
    opacity: 1;
  }
  30% {
    opacity: 1;
  }
  35% {
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}

.descripcionProyecto > p {
  color: #03045e;
}
.descripcionProyecto {
  width: 95%;
  margin: 1rem;
}
.descripcionProyecto > img {
  width: 40px;
  margin-right: 2px;
}
.tools {
  display: flex;
  align-items: center;
  gap: 6px;
  margin-bottom: 8px;
}
.tools > *:last-child {
  margin-left: auto; 
}
.tools img {
  width: 40px;
}

.btnDescargar {
  width: 40px;
  height: 40px;
  background: #03045e;
  color: white;
  border: none;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: 0.2s ease;
}
.btnDescargar:hover {
  background: #fc4b08;
}
.btnDescargar svg {
  width: 24px;
  height: 24px;
}
p > a {
  margin-right: 10px;
  text-decoration: none;
  color: #fc4b08;;
}
p > a:hover{
  color: #023e8a;
}
</style>
