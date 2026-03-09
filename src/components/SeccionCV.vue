<script setup>
defineProps({
  titulo: String,
  items: Array
});
</script>

<template>
  <section class="seccion">
    <div class="col-izq" v-html="titulo.replace(' ', '<br>')"></div>
    
    <div class="col-der">
      <div v-for="(item, index) in items" :key="index" class="item">
        
        <div v-if="item.principal" class="fila-titulo">
          <strong>{{ item.principal }}</strong>
          <span v-if="item.fecha">{{ item.fecha }}</span>
        </div>
        
        <p v-if="item.secundario" class="empresa">{{ item.secundario }}</p>
        <p v-if="item.descripcion">{{ item.descripcion }}</p>
        
        <ul v-if="item.detalles">
          <li v-for="(detalle, i) in item.detalles" :key="i">{{ detalle }}</li>
        </ul>
        
      </div>
    </div>
  </section>
  <hr />
</template>

<style scoped>
.seccion { display: flex; }
.col-izq { width: 25%; font-style: italic; color: #040101; font-size: 1rem; }
.col-der { width: 75%; font-size: 0.95rem; }
.item { margin-bottom: 20px; }
.fila-titulo { display: flex; justify-content: space-between; }
.empresa { color: #3b7cc8; font-weight: bold; margin: 2px 0; }
ul { font-size: 0.85rem; margin-top: 5px; color: #555; list-style-position: inside; }
hr {  border-top: 2px solid #eee; margin: 25px 0; }
</style>