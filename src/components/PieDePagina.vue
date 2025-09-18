<script setup></script>

<template>
  <footer class="footer">
    <p>&copy; 2025 Website Carmen Bedrule. All rights reserved.</p>
    <p>CREATED BY:</p>
    <a
      class="creador"
      href="https://www.linkedin.com/in/josemartinezgz98"
      target="_blank"
      title="LinkedIn"
      >www.linkedin.com/in/josemartinezgz98</a
    ><br/>

    <div class="social-icons">
      <a
        href="linkedin.com/in/josemartinezgz98"
        target="_blank"
        title="LinkedIn"
      >
        <i class="fab fa-linkedin"></i>
      </a>
      <a href="tel:+34691797404" title="Llamar al móvil">
        <i class="fas fa-phone"></i>
      </a>
      <a href="mailto:josesw98@gmail.com" title="Enviar correo">
        <i class="fas fa-envelope"></i>
      </a>
    </div>

    <img class="logo" src="/images/logo/logo6.png" />
  </footer>
</template>

<style scoped>
.footer {
  position: relative; 
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #03045e;
  padding: 10px;
  color: white;
  overflow: hidden;
}

.logo {
  position: absolute;
  top: 40%;
  left: 80%;
  transform: translate(-50%, -50%);
  opacity: 0.8; 
  width: 200px;
  height: auto;
  z-index: 0; 
  pointer-events: none; 
}

.footer p,
.footer .creador,
.footer .social-icons {
  position: relative;
  z-index: 1;
}

.social-icons {
  display: flex;
  justify-content: space-between;
  font-size: 2rem;
  width: 30%;
  margin-bottom: 20px;
}
.social-icons a {
  color: white;
  text-decoration: none;
}
.social-icons a:hover {
  color: #fc4b08;
}
.creador {
  text-decoration: none;
  color: white;
}
.creador:hover {
  text-decoration: none;
  color: #fc4b08;
}

@media (max-width: 768px) {
  .footer {
    max-width: 100%;
    margin-left: auto;
    margin-right: auto;
  }
  .logo {
    width: 150px;
  }
}

@media (max-width: 480px) {
  .footer {
    max-width: 100%;
    margin: 0 auto;
    padding: 10px 20px;
    box-sizing: border-box;
  }
  .social-icons {
    width: auto;
    max-width: none;
    justify-content: center;
    gap: 15px;
    margin: 0 auto;
    padding: 0;
  }
  .logo {
    width: 120px;
  }
}
</style>
