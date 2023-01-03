<script setup>
import Image from './Image.vue'
</script>

<script>

export default {
  data() {
    return {
      categorias: [
        { text: "Categoria", value: null, disabled: true },
        { text: "Coropletas AQI", value: "aqi" },
        { text: "Coropletas Crimen", value: "crimen" },
        { text: "HotSpots", value: "hotspot" },
        { text: "Thiessen Crimen", value: "thiessenCrimen" },
        { text: "Thiessen AQI", value: "thiessenAqi" },
        { text: "Categorias PM2.5", value: "categoria1" },
        { text: "Categorias Ozono", value: "categoria2" },
      ],
      categoriasPM2: [
        { text: "PM2.5", value: null },
        { text: "Valores R", value: "valoresR" },
        { text: "Valores P", value: "valoresP" },
        { text: "% / 10 puntos de AQI", value: "valoresAQI" },
      ],
      categoriasO: [
        { text: "Ozono", value: null },
        { text: "Valores R", value: "ozonoR" },
        { text: "Valores P", value: "ozonoP" },
        { text: "% / 10 puntos de AQI", value: "ozonoAQI" },
      ],
      anios: [
        { text: "Año", value: null },
        { text: "2016", value: "2016" },
        { text: "2017", value: "2017" },
        { text: "2018", value: "2018" },
        { text: "2019", value: "2019" },
        { text: "2020", value: "2020" },
      ],
      meses: [
        { text: "Mes", value: null },
        { text: "Enero", value: "Enero" },
        { text: "Febrero", value: "Febrero" },
        { text: "Marzo", value: "Marzo" },
        { text: "Abril", value: "Abril" },
        { text: "Mayo", value: "Mayo" },
        { text: "Junio", value: "Junio" },
        { text: "Julio", value: "Julio" },
        { text: "Agosto", value: "Agosto" },
        { text: "Septiembre", value: "Septiembre" },
        { text: "Octubre", value: "Octubre" },
        { text: "Noviembre", value: "Noviembre" },
        { text: "Diciembre", value: "Diciembre" },
      ],
      selected1: null,
      selected: null,
      selected2: null,
      selected3: null,
      selected4: null
    };
  },
  methods: {
    clear() {
      // this.selected1 = null
      // this.selected2 = null
      if (this.selected3 != null) {
        this.selected3 = this.selected3
      }else{
        this.selected3 = null
      }
    }
  }
};

</script>
        
    
<template>
  <!-- <div class="container p-5"> -->
    <!-- <div class="row"> -->
      
    <!-- </div> -->

    <section>
        <div class="row">
          <div class="col-xl-3 col-sm-6 col-12 mb-4">
            <div class="card">
              <div class="card-body">
                <div class="d-flex justify-content-between px-md-1">
              
                    <!-- Primer Select(categorias) -->
                    <div class="col-md-auto">
                      <select
                        v-model="selected1"
                        class="form-select"
                        aria-label=".form-select-lg example"
                      >
                        <option
                          v-for="categoria in categorias"
                          :value="categoria.value"
                          :key="categoria.id"
                        >
                          {{ categoria.text }}
                        </option>
                      </select>
                    </div>
                  
                </div>
              </div>
            </div>
          </div>
          <div class="col-xl-2 col-sm-6 col-12 mb-4" v-if="
                        selected1 === 'categoria1'
                      ">
            <div class="card">
              <div class="card-body" >
                <div class="d-flex justify-content-between px-md-1">
                  <div class="align-self-center">
                    <!-- Tercer Select(mes) si la categoria lo permite -->
                    <div
                      class="col-md-auto"
                      
                    >
                      <select
                        v-model="selected3"
                        class="form-select"
                        aria-label=".form-select-lg example"
                      >
                        <option v-for="cat in categoriasPM2" :value="cat.value" :key="cat.id">
                          {{ cat.text }}
                        </option>
                      </select>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-xl-2 col-sm-6 col-12 mb-4" v-if="
                        selected1 === 'categoria2'
                      ">
            <div class="card">
              <div class="card-body" >
                <div class="d-flex justify-content-between px-md-1">
                  <div class="align-self-center">
                    <!-- Tercer Select(mes) si la categoria lo permite -->
                    <div
                      class="col-md-auto"
                      
                    >
                      <select
                        v-model="selected3"
                        class="form-select"
                        aria-label=".form-select-lg example"
                      >
                        <option v-for="cat in categoriasO" :value="cat.value" :key="cat.id">
                          {{ cat.text }}
                        </option>
                      </select>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-xl-2 col-sm-6 col-12 mb-4">
            <div class="card">
              <div class="card-body">
                <div class="d-flex justify-content-between px-md-1">
                  <div class="align-self-center">
                      <!-- Segundo Select(anio) -->
                  
                        <div class="col-md-auto">
                          <select id="archivo2"
                            v-model="selected2"
                            class="form-select"
                            aria-label=".form-select-lg example"
                          >
                            <option v-for="anio in anios" :value="anio.value" :key="anio.id">
                              {{ anio.text }}
                            </option>
                          </select>
                        </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-xl-2 col-sm-6 col-12 mb-4" v-if="
                        selected1 === 'aqi' ||
                        selected1 === 'crimen' ||
                        selected1 === 'hotspot'
                      ">
            <div class="card">
              <div class="card-body" >
                <div class="d-flex justify-content-between px-md-1">
                  <div class="align-self-center">
                    <!-- Tercer Select(mes) si la categoria lo permite -->
                    <div
                      class="col-md-auto"
                      
                    >
                      <select
                        v-model="selected3"
                        class="form-select"
                        aria-label=".form-select-lg example"
                      >
                        <option v-for="mes in meses" :value="mes.value" :key="mes.id">
                          {{ mes.text }}
                        </option>
                      </select>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-xl-2 col-sm-6 col-12 mb-4" v-if="selected1 != null && selected2 != null">
            <div class="card">
              <div class="card-body">
                <div class="d-flex justify-content-between px-md-1">
                  <div class="align-self-center">
                    <!-- Boton para cambiar imagen -->
                    <div class="col-md-auto">
                      <button
                        type="button"
                        class="btn btn-outline-success"
                        
                        @click="$refs.child.log(); clear()"
                      >
                        Buscar
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
    </section>
    <!-- <div class="row p-5"> -->
      <!-- <Image /> -->
     <div class="container">
        <div class="mx-auto">
          <Image ref="child" :cat="this.selected1" :year="selected2" :month="selected3" />
       </div>
     </div>
    <!-- </div> -->
  <!-- </div> -->
</template>
