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
        
        <sidebar/>

        <div class="col-md-10 panel">
          <div class="row justify-content-between top">
            <div class="col-md-6 breadcumbs">
              <span class="float-left">Inicio</span>
            </div>
            <div class="col-md-6 right">
              <a href="#" class="btn btn-primary btn-sm">Encuesta</a>
            </div>
          </div>

          <div class="reporte pt-4" id="printableArea">
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

            <div class="row cuadro-g mt-2">
              <p><strong>Detalles Generales</strong></p>
              <div class="col-md-2 bold">
                <p>Afiliado:</p>
                <p>No de Cita:</p>
                <p>Centro Médico:</p>
              </div>
              <div class="col-md-3">
                <p class="t-gris">Ryan Pineda</p>
                <p class="t-gris">0533</p>
                <p class="t-gris">Clínica Periférica Calpules</p>
              </div>
              <div class="col-md-2 bold">
                <p>Vacuna:</p>
                <p>Fecha primera dosis:</p>
                <p>Fecha segunda dosis:</p>
              </div>
              <div class="col-md-3">
                <p class="t-gris">Pfizer</p>
                <p class="t-gris">10/05/2021</p>
                <p class="t-gris">10/06/2021</p>
              </div>
              <div class="col-md-2">
                <a href="3" class="btn btn-primary">Completado</a>
              </div>
            </div>

            <div class="citas" v-if="info != 'undefined'">
              <h6><strong>Información de Cita</strong></h6>
              <div class="row cuadro card-cita me-0" v-for="aff in info" :key="aff.idAfiliado">
                <p><strong class="t-blue">Información Dosis</strong></p>
                <div class="col-md-12">
                  <div class="row justify-content-between">
                    <div class="col-md-2 n-cita">
                      <span><strong>Cita - {{aff.idCita}}</strong></span>
                      <div class="row mt-3 justify-content-between">
                        <div class="col-md-12">
                          <img
                            src="~/assets/anya-taylor-joy-getty1-t.jpg"
                            alt=""
                          />
                          <span class="ms-3">{{aff.nombre}}</span>
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2 bold">
                      <p>Centro Médico:</p>
                      <p>Ciudad:</p>
                    </div>
                    <div class="col-md-2">
                      <p class="t-gris">Clínica Periférica Calpules</p>
                      <p class="t-gris">San Pedro Sula</p>
                    </div>
                    <div class="col-md-2 bold">
                      <p>Hora Prevista:</p>
                      <p>Vacuna:</p>
                    </div>
                    <div class="col-md-2">
                      <p class="t-gris">7:30 am</p>
                      <p class="t-gris">Pfizer</p>
                    </div>
                    <div class="col-md-2">
                      <a href="#" class="btn btn-primary">Completado</a>
                    </div>
                  </div>
                </div>
              </div>
              
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
export default {
  data() {
    return {
      info: null,
    }
  },
  mounted() {
    axios
      .get('http://192.241.138.101:5560/api/Appointment/afiliado/1')
      .then((response) => (this.info = response.data))
  },
}
</script>