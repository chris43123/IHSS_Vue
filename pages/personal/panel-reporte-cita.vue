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
        
        <sidebar-p />

        <div class="col-md-10 panel">
          <div class="row justify-content-between top">
            <div class="col-md-6 breadcumbs">
              <span class="float-left">Inicio</span>
            </div>
            <div class="col-md-6 right">
              <a href="#" class="btn btn-primary btn-sm">Encuesta</a>
            </div>
          </div>

          <div class="row formulario">
            <div class="col-md-6">
                <div class="row">
                  <div class="col-md-6">
                    <label for="#">Afiliado:</label>
                    <input type="text"  pattern="[0-9]{5}" v-model="search.text" />
                    <button v-on:click="buscar()" class="btn btn-primary btn-sm mt-2">Buscar</button>
                  </div>
                </div>
            </div>
          </div>

          <div class="reporte mt-4 pt-4" id="printableArea">
            <div class="row">
              <div class="col-md-6 logo">
                <img src="~/assets/ihss.jpg" alt="" />
              </div>
              <div class="col-md-6">
                <div class="row dato-reporte">
                  <div class="col-md-4 dato">
                    <span>Frecuencia: </span> Mensual
                  </div>
                  <div class="col-md-4 dato">
                    <span>No reporte: </span> 0245
                  </div>
                  <div class="col-md-4 dato">
                    <span>Emitido: </span> 12/04/2021
                  </div>
                </div>
              </div>
            </div>
            <div class="row mt-4">
              <h4>Reporte Individual de Cita</h4>
              <p>Datos correspondientes al 31 de diciembre de 2021</p>
            </div>

            

            <div v-if="!!citas">
              <detalle-cita
                :nombre="citas[0].nombre"
                :idAfiliado="citas[0].idAfiliado"
                :centroMedico="citas[0].centroMedico"
                :pfecha="citas[0].fecha"
                :sfecha="citas[1] ? citas[1].fecha : null"
                :vacuna="citas[0].vacuna"
              />
            </div>

            <div class="citas" v-if="citas != 'undefined'">
              <h6><strong>Información de Cita</strong></h6>
                <info-cita
                  v-for="cita of citas"
                  :key="cita.idCita"
                  :idCita="cita.idCita"
                  :nombre="cita.nombre"
                  :centroMedico="cita.centroMedico"
                  :fecha="cita.fecha"
                  :aplicada="cita.aplicada"
                  :vacuna="cita.vacuna"
                />
            </div>

            <div class="row descargar">
              <div class="col-md-12">
                <input type="button" class="btn btn-primary" onclick="printDiv('printableArea')" value="Descargar">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <script src="../js/dropdown.js"></script>
    <script src="../js/imprimir.js"></script>
    <script
      src="https://kit.fontawesome.com/5883557ab1.js"
      crossorigin="anonymous"
    ></script>
  </div>
</template>

<script>
import axios from 'axios'
import infoCita from '~/components/info-cita.vue'
import DetalleCita from '~/components/detalle-cita.vue'
export default {
  components: { infoCita, DetalleCita },
  data() {
    return {
      search: {},
      citas: null,
      info: null,
      status: null
    }
  },
  async created() {
    try {
      const r1 = await axios.get('http://192.241.138.101:5560/api/Appointment/afiliado/' + this.$route.query.idAfiliado)
      this.citas =  r1.data;
      if(r1.data.length == 0){
        console.log("Arreglo vacio")
      }

    } catch (error) {
      console.log(error);
    }
  },
  methods:{
      buscar()
      {
        axios
        .get('http://192.241.138.101:5560/api/Appointment/afiliado/'+this.search.text)
        .then((response) => {this.citas = response.data;
            this.status = response.status
        })
      },
  },
}
</script>