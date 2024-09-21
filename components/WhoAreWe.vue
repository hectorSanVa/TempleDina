<template>
  <div class="whoarewe-container">
    <div class="image-content-wrapper">
      <div class="image-section">
        <!-- Aquí se coloca la ruta directa a la imagen -->
        <img src="/Compu2.png" alt="Laptop Image" />
      </div>
      <div class="content-section">
        <h1 class="section-title">Nosotros!!</h1>
        <p class="section-description">{{ data.description }}</p>
      </div>
    </div>
    <div class="features">
      <div v-for="(feature, index) in data.features" :key="index" class="feature">
        <i :class="feature.icon" class="social-icon" :style="{ color: feature.iconColor }"></i>
        <div class="feature-text">
          <h2>{{ feature.title }}</h2>
          <p>{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from '@/assets/styles/WhoAreWe.json'; // Asegúrate de que el JSON está en la ruta correcta

export default {
  name: 'WhoAreWe',
  data() {
    return {
      data, // Cargamos los datos del JSON
    };
  }
};
</script>

<!-- Importar el CSS externo -->
<style src="@/assets/styles/WhoAreWe.css"></style>