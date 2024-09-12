<template>
  <footer class="footer" :style="footerStyle">
    <div class="footer-section">
      <h4>¿QUÉ HACEMOS?</h4>
      <ul class="footer-list">
        <li>Webs corporativas</li>
        <li>Desarrollo web a medida</li>
        <li>Tiendas online</li>
        <li>Marketing online</li>
        <li>Consultoría de desarrollo web</li>
      </ul>
    </div>

    <div class="footer-section">
      <h4>SÍGUENOS EN REDES</h4>
      <div class="social-links">
        <a href="mailto:example@example.com" target="_blank" rel="noopener noreferrer" aria-label="Correo Electrónico">
          <i class="fa-solid fa-envelope social-icon" style="color: #6c759d;"></i>
        </a>
        <a href="https://facebook.com/tuperfil" target="_blank" rel="noopener noreferrer" aria-label="Facebook">
          <i class="fa-brands fa-facebook social-icon" style="color: #4267b2;"></i>
        </a>
        <a href="https://instagram.com/tuperfil" target="_blank" rel="noopener noreferrer" aria-label="Instagram">
          <i class="fa-brands fa-instagram social-icon" style="color: #c13584;"></i>
        </a>
        <a href="https://wa.me/9622242393" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp">
          <i class="fa-brands fa-whatsapp social-icon" style="color: #25d366;"></i>
        </a>
      </div>
    </div>

    <div class="footer-section">
      <h4>¿NOS CUENTAS TU PROYECTO?</h4>
      <p>Ensalza: agencia de desarrollo y diseño web</p>
      <p>Dirección: Calle Falsa 123, Ciudad, País</p>
      <p>Tel: +52 5657895551</p>
      <p>Mail: info@ensalza.com</p>
    </div>

    <p class="footer-links">
      <a href="#" data-bs-toggle="modal" data-bs-target="#termsModal">Términos y Condiciones</a> | 
      <a href="#" data-bs-toggle="modal" data-bs-target="#privacyModal">Aviso de Privacidad</a>
    </p>

    <ModalTerms />
    <ModalPrivacy />

    <p class="footer-copyright">
      © {{ new Date().getFullYear() }} Devpilots. Todos los derechos reservados.
    </p>
  </footer>
</template>

<script>
import colors from '~/assets/styles/colors.json';
import ModalTerms from '~/components/ModalTerms.vue';
import ModalPrivacy from '~/components/ModalPrivacy.vue';

export default {
  components: {
    ModalTerms,
    ModalPrivacy,
  },
  computed: {
    footerStyle() {
      return {
        backgroundColor: colors.footer.backgroundColor || '#2c3e50',
        color: colors.footer.textColor || '#ffffff',
      };
    },
  },
};
</script>

<style scoped>
.footer {
  padding: 20px 5%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 20px;
  background-color: #2c3e50;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
}

.footer-section {
  flex: 1 1 150px;
  min-width: 120px;
  max-width: 200px;
  margin-bottom: 15px; /* Reduce el espacio entre secciones en pantallas grandes */
  text-align: center; /* Centra el contenido */
}

.footer-section h4 {
  font-size: 1em;
  margin-bottom: 10px;
  color: #ffffff;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.footer-list {
  list-style: none;
  padding: 0;
  margin: 0;
  color: #d1d1d1;
  font-size: 0.9em;
}

.footer-list li {
  margin-bottom: 5px;
}

.social-links {
  display: flex;
  gap: 10px; /* Reduce el espacio entre los iconos de redes sociales */
  margin: 10px 0;
  justify-content: center; /* Centra los iconos de redes sociales */
}

.social-icon {
  font-size: 1.3em; /* Ajusta el tamaño de los iconos */
  transition: transform 0.3s, color 0.3s;
}

.social-icon:hover {
  transform: scale(1.2);
  filter: brightness(1.2);
}

.footer-links {
  text-align: center;
  width: 100%;
  font-size: 0.75em; /* Ajusta el tamaño del texto en enlaces */
  color: #b0b0b0;
  margin-top: 10px;
}

.footer-links a {
  text-decoration: none;
  color: #b0b0b0;
  padding: 0 4px; /* Reduce el espacio entre enlaces */
  transition: color 0.3s, text-decoration 0.3s;
}

.footer-links a:hover {
  color: #ffffff;
  text-decoration: underline;
}

.footer p {
  margin: 0;
  font-size: 0.8em;
  line-height: 1.5;
}

.footer-section p {
  margin: 2px 0; /* Reduce el espacio entre párrafos */
}

.footer h4 {
  margin: 5px 0;
}

.footer-copyright {
  text-align: center;
  width: 100%;
  font-size: 0.7em;
  color: #d1d1d1;
  margin-top: 5px; /* Reduce el espacio en la parte superior */
}

@media (max-width: 576px) {
  .footer {
    padding: 15px;
    flex-direction: column;
    align-items: center;
  }
  .footer-section {
    max-width: 100%; /* Asegura que las secciones ocupen toda la anchura disponible */
    margin-bottom: 10px; /* Reduce el espacio entre secciones en móviles */
  }
  .social-icon {
    font-size: 1.2em; /* Ajusta el tamaño de los iconos en móviles */
  }
  .footer-links {
    font-size: 0.7em; /* Ajusta el tamaño del texto en enlaces en móviles */
  }
}
</style>
