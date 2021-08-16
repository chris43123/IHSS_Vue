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

          <div class="row">
            <div class="col-md-6">
              <h4>Reporte Paciente</h4>
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

          <div class="reporte paciente mt-4" id="imprimir" v-if="!!info">
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
              <h4 class="t-gris">Reporte Individual de Paciente</h4>
              <div class="separar"></div>
            </div>
            
            <div  v-if="info != 'undefined'">
              <info-personal-paciente
                :idAfiliado = "info.idAfiliado"
                :nombre = "info.nombre"
                :apellidos = "info.apellidos"
                :fechaNacimiento = "info.fechaNacimiento"
                :nacionalidad = "info.nacionalidad"
                :sexo = "info.sexo"
                :direccion = "info.direccion"
                :noIdentidad = "info.noIdentidad"
                :fechaAfiliacion = "info.fechaAfiliacion"
                :empresa = "info.empresa"
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

            <div class="row">
              <h4 class="text-center">Detalle de Enfermedades Base</h4>
            </div>
            <div class="row">
              <div class="col-md-12">
                <div class="row cuadro">
                  <h6 class="pb-3">Enfermedades pulmonares</h6>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#"
                          >Enfermedad pulmonar obstructiva crónica (EPOC)</label
                        >
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Cancer Pulmón</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#">Fibrosis quistica</label>
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Fibrosis Pulmonar</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Asma moderada-grave</label>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="row">
              <div class="col-md-12">
                <div class="row cuadro">
                  <h6 class="pb-3">Enfermedades pulmonares</h6>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#"
                          >Enfermedad pulmonar obstructiva crónica (EPOC)</label
                        >
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Cancer Pulmón</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#">Fibrosis quistica</label>
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Fibrosis Pulmonar</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Asma moderada-grave</label>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="row">
              <div class="col-md-12">
                <div class="row cuadro">
                  <h6 class="pb-3">Enfermedades pulmonares</h6>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#"
                          >Enfermedad pulmonar obstructiva crónica (EPOC)</label
                        >
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Cancer Pulmón</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" checked />
                        <label for="#">Fibrosis quistica</label>
                      </div>
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Fibrosis Pulmonar</label>
                      </div>
                    </div>
                  </div>
                  <div class="col-md-4">
                    <div class="row checkbox">
                      <div class="col-md-12 pb-3">
                        <input type="checkbox" />
                        <label for="#">Asma moderada-grave</label>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="row descargar">
              <div class="col-md-12">
                <a href="#" class="btn btn-primary btn-sm"
                  ><i class="fas fa-download"></i> Download</a
                >
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
import infoPersonalPaciente from '~/components/info-personal-paciente.vue'
export default {
  components: { infoPersonalPaciente },
  data() {
    return {
      search: {},
      info: null,
      citas: null,
    }
  },
  methods:{
      buscar()
      {
        axios
          .get('http://192.241.138.101:5560/api/Affiliates/'+this.search.text)
          .then((response) => {this.info = response.data
            axios
              .get('http://192.241.138.101:5560/api/Appointment/afiliado/' + this.info.idAfiliado)
              .then((response) => (this.citas = response.data))
          })
      },
  },
}
</script>