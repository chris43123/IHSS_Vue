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
        <sidebar-jc />

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
            <div class="row info-paciente mt-4">
              <div class="col-md-3 imagen">
                <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="" />
              </div>
              <div class="col-md-4">
                <h5>Información Personal</h5>
                <div class="row pt-3">
                  <div class="col-md-6 bold">
                    <p>Nombre:</p>
                    <p>Apellidos:</p>
                    <p>Fecha de Nacimiento:</p>
                    <p>Nacionalidad:</p>
                    <p>Sexo:</p>
                    <p>Dirección:</p>
                    <p>Identidad:</p>
                  </div>
                  <div class="col-md-6">
                    <p class="t-gris">{{info.nombre}}</p>
                    <p class="t-gris">{{info.apellidos}}</p>
                    <p class="t-gris">{{toDate(info.fechaNacimiento)}}</p>
                    <p class="t-gris">{{info.nacionalidad}}</p>
                    <p class="t-gris">{{info.sexo}}</p>
                    <p class="t-gris">{{info.direccion}}</p>
                    <p class="t-gris">{{info.noIdentidad}}</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4">
                <h5>Información Adicional</h5>
                <div class="row pt-3">
                  <div class="col-md-6 bold">
                    <p>Número Seguro:</p>
                    <p>Fecha de Afiliación:</p>
                    <p>Empresa:</p>
                  </div>
                  <div class="col-md-6">
                    <p class="t-gris">{{info.idAfiliado}}</p>
                    <p class="t-gris">{{toDate(info.fechaAfiliacion)}}</p>
                    <p class="t-gris">{{info.empresa}}</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4"></div>
            </div>

            <div class="citas" v-if="cita != 'undefined'">
              <h6><strong>Información de Cita</strong></h6>
              <div class="row cuadro card-cita me-0" v-for="aff in cita" :key="aff.idAfiliado">
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
                      <p class="t-gris">{{aff.centroMedico}}</p>
                      <p class="t-gris">San Pedro Sula</p>
                    </div>
                    <div class="col-md-2 bold">
                      <p>Hora Prevista:</p>
                      <p>Vacuna:</p>
                    </div>
                    <div class="col-md-2">
                      <p class="t-gris">{{ toHours(aff.fecha) }}</p>
                      <p class="t-gris">{{aff.vacuna}}</p>
                    </div>
                    <div class="col-md-2">
                      <span class="btn btn-primary" v-if="aff.aplicada">Completado</span>
                      <span class="btn btn-gray" v-else>Pendiente</span>
                    </div>
                  </div>
                </div>
              </div>
              
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
export default {
  data() {
    return {
      search: {},
      info: null,
      cita: null,
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
              .then((response) => (this.cita = response.data))
          })
      },
      toDate(date) {
        var your_date_object = new Date()
        your_date_object.setTime(Date.parse(date))

        var date = your_date_object.getDate()
        var month = your_date_object.getMonth()
        var year = your_date_object.getFullYear()
        return date+ '/' + month + '/' + year; 
    },
    toHours(date) {
      var your_date_object = new Date()
      your_date_object.setTime(Date.parse(date))

      var min = your_date_object.getMinutes()
      var hour = your_date_object.getHours()
      return (hour < 10 ? '0'+hour:hour) + ':' + (min<10 ? '0'+min:min) 
    },
  },
}
</script>