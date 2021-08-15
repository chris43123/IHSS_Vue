<template>
  <div>
    <div class="nav">
      <div class="item-left">
        <a href="#"><i class="fas fa-th-large"></i></a>
        <a href="#">Gerente</a>
      </div>
      <div class="item-right">
        <a href="#"><i class="fas fa-bell"></i></a>
        <a href="#"><i class="fas fa-question-circle"></i></a>
        <a href="#"><i class="fas fa-cog"></i></a>
        <a href="#"
          ><img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt=""
        /></a>
      </div>
    </div>

    <div class="container-fluid">
      <div class="row">
        <sidebar />

        <div class="col-md-10 panel">
          <div class="row justify-content-between top">
            <div class="col-md-6 breadcumbs">
              <span class="float-left">Inicio</span>
            </div>
            <div class="col-md-6 right">
              <a href="#" class="btn btn-primary btn-sm">Encuesta</a>
            </div>
          </div>

          <div class="row justify-content-between info">
            <div class="col-md-6">
              <h4>Hola, Valentina Flores</h4>
            </div>
            <div class="col-md-6 right">
              <h4>23, septiembre 2021</h4>
            </div>
          </div>
           
          <div class="row citas">
            <h6>Listado de citas diarias</h6>
            <div class="col-md-12">
              <div class="row" v-if="info != 'undefined'">
                  
                <div
                  class="col-md-5 cuadro-sm card-cita m-2"
                  v-for="aff in info"
                  :key="aff.idAfiliado"
                >
                  <div class="row justify-content-between pb-3">
                    <div class="col-md-4 n-cita">
                      <span
                        ><strong>Cita - {{ aff.idAfiliado }}</strong></span
                      >
                    </div>
                    <div class="col-md-4 text-center">
                      <span>Hora:</span> {{ toHours(aff.fecha) }}
                    </div>
                    <div class="col-md-4 text-end">
                      <span>Vacuna:</span> {{ aff.idVacuna }}
                    </div>
                  </div>
                  <div class="row justify-content-between">
                    <div class="col-md-6">
                      <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="" />
                      <span class="ms-3">{{ aff.nombre }}</span>
                    </div>
                    <div class="col-md-6 text-end">
                      <router-link :to="{ path: 'panel-reporte-cita', query: {idAfiliado: aff.idAfiliado }}">Ver detalles</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <script src="../js/dropdown.js"></script>
    <script
      src="https://kit.fontawesome.com/5883557ab1.js"
      crossorigin="anonymous"
    ></script>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      info: null,
    }
  },
  methods: {
    toHours(date) {
      var your_date_object = new Date()
      your_date_object.setTime(Date.parse(date))

      var min = your_date_object.getMinutes()
      var hour = your_date_object.getHours()
      return (hour < 10 ? '0'+hour:hour) + ':' + (min<10 ? '0'+min:min) 
    },
  },
  mounted() {
    axios
      .get('http://192.241.138.101:5560/api/Appointment/1')
      .then((response) => (this.info = response.data))
  },
}
</script>