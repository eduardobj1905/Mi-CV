<script setup>

import SeccionCV from './components/SeccionCV.vue';

const cabecera = {
  nombre: "EDUARDO BERNAL JIMENEZ",
  puesto: "Desarrollador de Aplicaciones Multiplataforma",
  contacto: {
    ubicacion: "Madrid, España",
    telefono: "+34 611465090",
    email: "eduardobernal1502@gmail.com",
    github: "https://github.com/eduardobj1905"
  }
};

const seccionesCV = [
  {
    titulo: "Habilidades",
    items: [
      { descripcion: ["Java", "Python", "HTML/CSS", "Spring Boot", "SQL", "Git", "Docker", "MongoDB"].join(' · ') }
    ]
  },
  {
    titulo: "Experiencia Laboral",
    items: [
      {
        principal: "Desarrollo de Software (Prácticas)",
        secundario: "Experis IT",
        fecha: "2025",
        detalles: [
          "Colaboración en el desarrollo de una aplicación en equipo, realizando tareas básicas como pruebas con Postman, documentación de procesos y organización de archivos.",
          "Uso de herramientas como Git para control de versiones, Docker para gestionar entornos, y Eclipse como IDE.", 
          "Aprendizaje sobre flujos de trabajo en equipo, pruebas de funcionalidades y familiarización con buenas prácticas."
        ]
      },
      {
        principal: "Vendedor y gestión de equipos",
        secundario: "Foot Locker",
        fecha: "2017 - Actualidad",
        detalles: [
          "Atención personalizada al cliente, asesoramiento comercial y cumplimiento de objetivos de venta.",
          "Responsable del control de stock, organización del punto de venta y uso de herramientas digitales.",
          "Desarrollo de habilidades clave como liderazgo, trabajo bajo presión, comunicación efectiva y toma de decisiones."
        ]
      }
    ]
  },
  {
    titulo: "Formación",
    items: [
      { principal: "Grado Superior de DAM", secundario: "Davante Fuenlabrada", fecha: "Junio 2026" }
    ]
  },
  {
    titulo: "Certificaciones y cursos",
    items: [
      { descripcion: "AWS Cloud Quest: Cloud Practitioner" },
      { descripcion: "Responsive Web Design - FreeCodeCamp" },
      { descripcion: "Universidad de Java Cero - Experto - Udemy" }
    ]
  }
];
</script>

<template>
  <div class="background">
    <div class="hoja">
      
      <header class="header">
        <h1>{{ cabecera.nombre }}</h1>
        <p class="subtitulo">{{ cabecera.puesto }}</p>
        <div class="contacto">
          {{ cabecera.contacto.ubicacion }} | {{ cabecera.contacto.telefono }} |
          <a :href="'mailto:' + cabecera.contacto.email">{{ cabecera.contacto.email }}</a> | 
          <a :href="cabecera.contacto.github" target="_blank">GitHub</a>
        </div>
      </header>

      <hr />

      <SeccionCV 
        v-for="seccion in seccionesCV" 
        :key="seccion.titulo" 
        :titulo="seccion.titulo" 
        :items="seccion.items" 
      />

    </div>
  </div>
</template>

<style scoped>
.background { background-color: #5682d4; min-height: 100vh; padding: 40px 20px; display: flex; justify-content: center; }
.hoja { max-width: 800px; width: 100%; background: white; padding: 50px; box-shadow: 0 0 20px rgba(0,0,0,0.1); font-family: Arial, sans-serif; color: #333; border-radius: 20px; }
.header { text-align: center; }
h1 { letter-spacing: 3px; font-weight: 300; margin-bottom: 5px; font-size: 2rem; }
.subtitulo { font-style: italic; color: #242323; margin-bottom: 10px; }
.contacto { font-size: 0.9rem; color: #7c7575; }
hr { border: 0; border-top: 2px solid #eee; margin: 25px 0; }
</style>