<template>
  <div>
    <Header :isScrolled="isScrolled" />
    <section id="inicio" class="bg-dark text-white text-center d-flex align-items-center justify-content-center position-relative" style="height: 100vh;">
      <!-- Contenido para la sección de Inicio -->
      <!--
      <video autoplay loop muted class="w-100 h-100 object-fit-cover">
        <source src="/costa rica.mp4" type="video/mp4">
        Tu navegador no soporta el formato de video.
      </video>
      -->
      <HeroSlideshow />
    </section>
    <section id="quienes-somos" class="py-5 bg-light">
      <!-- Contenido para la sección de ¿Quiénes somos? -->
      <div class="container">
        <h2 class="text-center mb-4">¿Quiénes Somos?</h2>
        <p class="text-center">Aquí va una breve descripción sobre nosotros.</p>
      </div>
    </section>
    <section id="la-plataforma" class="py-5">
      <!-- Contenido para la sección de La plataforma -->
      <div class="container">
        <h2 class="text-center mb-4">La Plataforma</h2>
        <p class="text-center">Información sobre la plataforma.</p>
      </div>
    </section>
    <section id="contacto" class="py-5 bg-light">
      <!-- Contenido para la sección de Contacto -->
      <div class="container">
        <h2 class="text-center mb-4">Contacto</h2>
        <form>
          <div class="form-group">
            <label for="name">Nombre</label>
            <input type="text" class="form-control" id="name" placeholder="Tu nombre">
          </div>
          <div class="form-group">
            <label for="email">Correo electrónico</label>
            <input type="email" class="form-control" id="email" placeholder="Tu correo electrónico">
          </div>
          <div class="form-group">
            <label for="message">Mensaje</label>
            <textarea class="form-control" id="message" rows="3" placeholder="Tu mensaje"></textarea>
          </div>
          <button type="submit" class="btn btn-primary">Enviar</button>
        </form>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import HeroSlideshow from '@/components/HeroSlideshow.vue';
import { ref, onMounted, onUnmounted } from 'vue';

export default {
  components: {
    Header,
    Footer,
    HeroSlideshow
  },
  setup() {
    const isScrolled = ref(false);

    const handleScroll = () => {
      isScrolled.value = window.scrollY > 50;
    };

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });

    return {
      isScrolled
    };
  }
};
</script>

<style scoped>
/* Estilos globales o específicos para app.vue */

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: #fff;
  z-index: 3; /* Asegura que el overlay se muestre por encima del video y slideshow */
}

video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1; /* Asegura que el video esté detrás del slideshow y overlay */
}
</style>
