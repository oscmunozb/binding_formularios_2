<!-- Script JS -->
<script setup>
// Importamos 'ref' de Vue para crear variables reactivas
import { ref } from 'vue';

// Declaración de variables reactivas que se utilizarán en el formulario
const titulo = ref('Estoy aprendiendo Vue Js'); // Título principal que se mostrará
const emoji = ref('👨🏻‍💻'); // Emoji seleccionado por el usuario
const apreciacion = ref('Increible'); // Opinión sobre lo aprendido
const competencias = ref([
  "Morfología de un componente",
  "One-Way y Two-Way data binding",
  "El patrón de diseño MVVM",
  "Directivas",
  "Estado"]); // Lista de competencias aprendidas
const opinion = ref('Ahora podré desarrollar aplicaciones más cómodamente!!'); // Opinión personal sobre el framework
</script>

<!-- Template HTML -->
<template>
  <!-- Contenedor principal -->
  <main class="container-fluid pt-5">
    <div class="row">
      <!-- Columna para el formulario -->
      <div class="col-5">
        <!-- Formulario para modificar los valores reactivamente -->
        <form class="rounded-4 text-white bg-dark p-4 h-100">
          <!-- Campo para modificar el título -->
          <div class="d-flex">
            <label class="me-2" for="titulo">Título:</label>
            <div class="w-100">
              <input class="form-control" type="text" v-model="titulo" name="titulo" id="titulo"
                placeholder="Estoy aprendiendo Vue Js">
            </div>
          </div>
          <hr>
          <!-- Campo para seleccionar un emoji -->
          <div>
            <label for="emoji">Emoji: </label>
            <select class="ms-2" v-model="emoji" name="emoji" id="emoji">
              <option value="👨🏻‍💻">👨🏻‍💻</option>
              <option value="🗿">🗿</option>
              <option value="🕵">🕵</option>
              <option value="🤖">🤖</option>
            </select>
          </div>
          <hr>
          <!-- Campo para seleccionar la apreciación -->
          <div class="d-flex">
            <label>Apreciación: </label>
            <ul class="d-flex flex-wrap p-0 m-0">
              <!-- Opciones de apreciación usando botones de radio -->
              <li class="list-group-item ms-2">
                <input v-model="apreciacion" type="radio" name="regular" id="regular" value="Regular">
                <label class="ms-1" for="regular">Regular</label>
              </li>
              <li class="list-group-item ms-2">
                <input v-model="apreciacion" type="radio" name="bien" id="bien" value="Bien">
                <label class="ms-1" for="bien">Bien</label>
              </li>
              <li class="list-group-item ms-2">
                <input v-model="apreciacion" type="radio" name="muyBien" id="muyBien" value="Muy bien">
                <label class="ms-1" for="muyBien">Muy bien</label>
              </li>
              <li class="list-group-item ms-2">
                <input v-model="apreciacion" type="radio" name="increible" id="increible" value="Increible">
                <label class="ms-1" for="increible">Increible</label>
              </li>
            </ul>
          </div>
          <hr>
          <!-- Campo para seleccionar competencias aprendidas -->
          <div class="row">
            <label class="col-lg-3">Competencias <br> aprendidas: </label>
            <div class="col-lg-9 row">
              <div class="col-xl-7">
                <div>
                  <!-- Checkbox para la morfología de un componente -->
                  <input class="mt-2" v-model="competencias" type="checkbox" name="morfologia" id="morfologia"
                    value="Morfología de un componente">
                  <label class="align-top ms-1" for="morfologia">Morfología de un <br class="d-none d-xl-block">
                    componente</label>
                </div>
                <div>
                  <!-- Checkbox para One-Way y Two-Way data binding -->
                  <input v-model="competencias" type="checkbox" name="dataBinding" id="dataBinding"
                    value="One-Way y Two-Way data binding">
                  <label class="align-top ms-1" for="dataBinding">One-Way y Two-Way <br class="d-none d-xl-block"> data
                    binding</label>
                </div>
                <div>
                  <!-- Checkbox para el patrón de diseño MVVM -->
                  <input v-model="competencias" type="checkbox" name="patron" id="patron"
                    value="El patrón de diseño MVVM">
                  <label class="align-top ms-1" for="patron">El patrón de diseño <br class="d-none d-xl-block">
                    MVVM</label>
                </div>
              </div>
              <div class="col-xl-5">
                <div>
                  <!-- Checkbox para directivas -->
                  <input v-model="competencias" type="checkbox" name="directivas" id="directivas" value="Directivas">
                  <label class="align-top ms-1" for="directivas">Directivas</label>
                </div>
                <div>
                  <!-- Checkbox para estado -->
                  <input v-model="competencias" type="checkbox" name="estado" id="estado" value="Estado">
                  <label class="align-top ms-1" for="estado">Estado</label>
                </div>
              </div>
            </div>
          </div>
          <hr>
          <!-- Campo para escribir una opinión personal -->
          <div class="d-flex">
            <label class="me-2" for="opinion">Opninión: </label>
            <div class="w-100">
              <textarea class="form-control" v-model="opinion" name="opinion" id="opinion"
                placeholder="Ahora podré desarrollar aplicaciones más cómodamente!!"></textarea>
            </div>
          </div>
        </form>
      </div>
      <!-- Columna para mostrar los datos introducidos -->
      <section class="col-7">
        <div class="rounded-4 h-100 border border-dark border-2 p-4 text-center">
          <h3 class="pb-3">{{ emoji }}</h3> <!-- Mostrar el emoji seleccionado -->
          <h2 class="pb-3">{{ titulo }}</h2> <!-- Mostrar el título -->
          <h3 class="pb-3">Y me parece {{ apreciacion }}</h3> <!-- Mostrar la apreciación -->
          <h4 class="pb-2">He aprendido: </h4>
          <h4 class="pb-3">{{ competencias.join(' - ') }}</h4> <!-- Mostrar competencias aprendidas -->
          <h4 class="pb-3">Mi opinión hasta ahora del framework es: </h4>
          <h6 class="pb-3">{{ opinion }}</h6> <!-- Mostrar la opinión -->
        </div>
      </section>
    </div>
  </main>
</template>

<!-- Style CSS -->
<style scoped></style>
