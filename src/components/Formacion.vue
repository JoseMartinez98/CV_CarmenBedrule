<script setup>
import { reactive } from "vue";

// Datos provistos por el usuario
const items = reactive([
  {
    title: "Herramientas Avanzadas de Adobe Illustrator",
    institution: "ESTUDIVIR Centro de formación",
    date: "17/06/2025 – 27/07/2025",
    description:
      "Especialización en diseño vectorial y herramientas avanzadas de Adobe Illustrator.",
    grade: "9",
  },
  {
    title: "Diseño y gestión de proyectos culturales",
    institution: "Junta de Andalucía",
    date: "02/02/2025 – 02/05/2025",
    description:
      "Enfoque en la planificación y gestión de iniciativas culturales.",
    grade: "7,72",
  },
  {
    title: "Dinamización, programación, y desarrollo de acciones culturales",
    institution: "Junta de Andalucía",
    date: "01/07/2024 – 02/02/2025",
    bullets: [
      "Proyectos de animación cultural",
      "Programaciones culturales",
      "Marketing cultural",
      "Dinamización, programación y desarrollo de acciones culturales",
    ],
    grade: "7",
  },
  {
    title: "Diploma en contabilidad",
    institution: "S.C. BESTCOR TRAINING CENTER S.R.L",
    date: "01/11/2022 – 13/12/2022",
    description:
      "Formación en fundamentos de contabilidad aplicada a la gestión administrativa y financiera.",
    grade: "8,5",
  },
]);
</script>

<template>
  <section class="timeline-root">
    <div class="timeline-container">
      <h2 class="timeline-title">Formación:</h2>
      <div class="timeline-line" aria-hidden="true"></div>

      <div
        v-for="(item, i) in items"
        :key="i"
        :class="['timeline-item', i % 2 === 0 ? 'left' : 'right']"
      >
        <div class="card">
          <h3 class="card-title">{{ item.title }}</h3>
          <div class="card-sub">{{ item.institution }}</div>
          <div class="card-date">{{ item.date }}</div>
          <p class="card-desc" v-if="item.description">
            {{ item.description }}
          </p>

          <ul v-if="item.bullets && item.bullets.length" class="card-list">
            <li v-for="(b, bi) in item.bullets" :key="bi">{{ b }}</li>
          </ul>

          <div v-if="item.grade !== undefined" class="card-grade">
            Calificación final: <strong>{{ item.grade }}</strong>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
:root {
  --bg1: #0f0b12;
  --bg2: #19121c;
  --panel: rgba(115, 48, 71, 0.9);
  --muted: rgba(255, 255, 255, 0.65);
  --line: rgba(255, 255, 255, 0.06);
  --accent: #ff4faa;
}
.timeline-title {
  position: absolute;
  top: -100px; 
  left: 50%;
  transform: translateX(-50%);
  font-size: 40px;
  margin: 0;
  color: #03045e;
  text-shadow: 2px 2px 2px #023e8a;
}
.timeline-root {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 48px 20px;
  background: linear-gradient(180deg, var(--bg1) 0%, var(--bg2) 100%);
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto,
    "Helvetica Neue", Arial;
  color: white;
}

.timeline-container {
  position: relative;
  width: 100%;
  max-width: 1100px;
}

.timeline-line {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 6px;
  height: 100%;
  background-color: #fc4b08;
  box-shadow: 0 0 0 1px var(--line) inset;
  border-radius: 6px;
}

.timeline-item {
  position: relative;
  margin: 40px 0;
  padding: 0 20px;
  display: flex;
  width: 50%;
}

.timeline-item.left {
  left: 0.5%;
  justify-content: flex-end;
  transform: translateX(-6%);
  
}

.timeline-item.right {
  left: 46%;
  justify-content: flex-start;
  transform: translateX(6%);
  
}

.card {
  background-color: #03045e;
  border-radius: 14px;
  padding: 28px 30px;
  width: 420px;
  box-shadow: 0 10px 30px rgba(3, 1, 2, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.03);
}

.card-title {
  margin: 0 0 10px 0;
  font-size: 28px;
  font-weight: 800;
  line-height: 1.05;
}

.card-sub {
  color: var(--muted);
  margin-bottom: 8px;
  font-weight: 600;
}

.card-date {
  color: rgba(255, 255, 255, 0.35);
  font-size: 14px;
  margin-bottom: 14px;
}

.card-desc {
  color: rgba(255, 255, 255, 0.85);
  line-height: 1.5;
  margin-bottom: 12px;
}

.card-list {
  margin: 0 0 10px 16px;
  color: rgba(255, 255, 255, 0.9);
}

.card-grade {
  margin-top: 6px;
  color: rgba(255, 255, 255, 0.95);
}

@media (max-width: 760px) {
  .timeline-title {
    position: relative;
    top: 0;
    left: 0;
    transform: none;
    font-size: 28px;
    text-align: center;
    margin-bottom: 40px;
  }

  .timeline-container {
    padding-left: 40px; /* deja espacio para la línea */
  }

  .timeline-line {
    left: 16px;
    transform: none;
    width: 4px;
  }

  .timeline-item {
    width: 100%;
    left: 0 !important;
    transform: none !important;
    justify-content: flex-start;
    padding: 0;
    margin: 20px 0;
  }

  .card {
    width: 100%;
    max-width: 100%;
    padding: 18px 20px;
    font-size: 14px;
  }

  .card-title {
    font-size: 20px;
    line-height: 1.2;
  }

  .card-sub {
    font-size: 14px;
  }

  .card-date {
    font-size: 12px;
  }

  .card-desc,
  .card-list,
  .card-grade {
    font-size: 14px;
  }
}

</style>
