<script setup>
const datos = {
  nombre: "EDUARDO BERNAL JIMENEZ",
  puesto: "Desarrollador de Aplicaciones Multiplataforma",
  contacto: {
    ubicacion: "Madrid, España",
    telefono: "+34 611465090",
    email: "eduardobernal1502@gmail.com",
    github: "https://github.com/eduardobj1905"
  },
  habilidades: ["Java", "Python", "HTML/CSS", "Spring Boot", "SQL", "Git", "Docker", "MongoDB"],
  experiencia: [
    {
      empresa: "Experis IT",
      cargo: "Desarrollo de Software (Prácticas)",
      fecha: "2025",
      tareas: ["Colaboración en el desarrollo de una aplicación en equipo, realizando tareas básicas como pruebas con Postman, documentación de procesos y organización de archivos",
           "Uso de herramientas como Git para control de versiones, Docker para gestionar entornos, y Eclipse como entorno de desarrollo integrado (IDE).", 
           "Aprendizaje sobre flujos de trabajo en equipo, pruebas de funcionalidades y familiarización con buenas prácticas en un entorno de desarrollo ágil"]
    },
    {
      empresa: "Foot Locker",
      cargo: "Vendedor y gestión de equipos",
      fecha: "2017 - Actualidad",
      tareas: ["Atención personalizada al cliente, asesoramiento comercial y cumplimiento de objetivos de venta en un entorno dinámico y orientado a resultados.",
       "Responsable del control de stock, organización del punto de venta y uso de herramientas digitales para seguimiento de métricas comerciales.",
        "Desarrollo de habilidades clave como liderazgo, trabajo bajo presión, comunicación efectiva y toma de decisiones."]
    }
  ],
  formacion: {
    titulo: "Grado Superior de DAM",
    centro: "Davante Fuenlabrada",
    fecha: "Junio 2026"
  },
  certificaciones: {
    cert: "AWS Cloud Quest: Cloud Practitioner",
    cert2: "Responsive Web Design - FreeCodeCamp",
    cert3: "Universidad de Java Cero - Experto -Udemy"
  }
}
</script>

<template>
  <div class="background">
    <div class="hoja">
      <header class="header">
        <h1>{{ datos.nombre }}</h1>
        <p class="subtitulo">{{ datos.puesto }}</p>
        <div class="contacto">
          {{ datos.contacto.ubicacion }} | {{ datos.contacto.telefono }} |
          <a :href="'mailto:' + datos.contacto.email">{{ datos.contacto.email }}</a> | 
          <a :href="datos.contacto.github" target="_blank">GitHub</a>
        </div>
      </header>

      <hr />

      <section class="seccion">
        <div class="col-izq">Habilidades</div>
        <div class="col-der">
          <p>{{ datos.habilidades.join(' · ') }}</p>
        </div>
      </section>

      <hr />

      <section class="seccion">
        <div class="col-izq">Experiencia<br>Laboral</div>
        <div class="col-der">
          <div v-for="exp in datos.experiencia" :key="exp.empresa" class="item">
            <div class="fila-titulo">
              <strong>{{ exp.cargo }}</strong>
              <span>{{ exp.fecha }}</span>
            </div>
            <p class="empresa">{{ exp.empresa }}</p>
            <ul>
              <li v-for="tarea in exp.tareas" :key="tarea"> {{ tarea }}</li>
            </ul>
          </div>
        </div>
      </section>

      <hr />

      <section class="seccion">
        <div class="col-izq">Formación</div>
        <div class="col-der">
          <strong>{{ datos.formacion.titulo }}</strong>
          <p>{{ datos.formacion.centro }} ({{ datos.formacion.fecha }})</p>
        </div>
      </section>
    
      <hr />

      <section class="seccion">
        <div class="col-izq">Certificaciones y cursos </div>
        <div class="col-der">
        <ul>
          <li>{{ datos.certificaciones.cert }}</li>
          <li>{{ datos.certificaciones.cert2 }}</li>
          <li>{{ datos.certificaciones.cert3 }}</li>
        </ul>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.background { background-color: #5682d4;
 min-height: 100vh;padding: 40px 20px;
 display: flex;
 justify-content: center; }
.hoja { max-width: 800px;
  width: 100%;
  background: white;
  padding: 50px;
  box-shadow: 0 0 20px rgba(0,0,0,0.1); 
  font-family: Arial, sans-serif; 
  color: #333;
  border-radius: 20px; }
.header { text-align: center; }
h1 { letter-spacing: 3px; 
 font-weight: 300; 
 margin-bottom: 5px; 
 font-size: 2rem; }
.subtitulo { font-style: italic; color:
 #242323; 
 margin-bottom: 10px;  }
.contacto { font-size: 0.9rem;
 color: #7c7575; }
hr { border: 0; 
 border-top: 2px solid #eee; 
 margin: 25px 0; }
.seccion { display: flex; }
.col-izq { width: 25%; 
 font-style: italic;  color: #040101; 
 font-size: 1rem; }
.col-der { width: 75%; 
 font-size: 0.95rem; }
.item { margin-bottom: 20px; }
.fila-titulo { display: flex; 
 justify-content: space-between }
.empresa { color: #3b7cc8; 
 font-weight: bold; margin: 2px 0; }
ul { padding: 0; font-size: 0.85rem; 
margin-top: 5px; 
color: #555; }
</style>