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
                    <input type="text" required v-model="search.text" />
                    <button v-on:click="buscar()" class="btn btn-primary btn-sm mt-2">Buscar</button>
                  </div>
                </div>
            </div>
          </div>

          <div class="reporte paciente mt-4" id="imprimir">
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
                    <p class="t-gris">Anya</p>
                    <p class="t-gris">Taylor-Joy</p>
                    <p class="t-gris">11/05/1999</p>
                    <p class="t-gris">Hondureño</p>
                    <p class="t-gris">Femenino</p>
                    <p class="t-gris">San Pedro Sula</p>
                    <p class="t-gris">0501-1997-0000</p>
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
                    <p class="t-gris">1325</p>
                    <p class="t-gris">12/05/2014</p>
                    <p class="t-gris">Diunsa</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4"></div>
            </div>

            <div class="row citas">
              <div class="col-md-12">
                <div class="cuadro-g mt-4">
                  <h6><strong>Proceso de vacunación</strong></h6>
                  <p>23, septiembre 2021</p>
                  <div class="row cuadro-sm card-cita p-3">
                    <div class="col-md-10">
                      <div class="row justify-content-between pb-3">
                        <div class="col-md-4 n-cita">
                          <span><strong>Cita - 02135</strong></span>
                          <div class="espaciado"></div>
                          <div class="col-md-12">
                            <img
                              src="~/assets/anya-taylor-joy-getty1-t.jpg"
                              alt=""
                            />
                            <span class="ms-3">Anya Taylor</span>
                          </div>
                        </div>
                        <div class="col-md-4">
                          <span>Centro Médico:</span> Clínica Periférica
                          Calpules
                          <div class="espaciado"></div>
                          <span>Ciudad:</span> San Pedro Sula, Cortés
                        </div>
                        <div class="col-md-4">
                          <span>Hora Prevista:</span> 07:30 am
                          <div class="espaciado"></div>
                          <span>Vacuna:</span> Pfizer
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2">
                      <a href="#" class="btn btn-primary btn-sm">Completado</a>
                    </div>
                  </div>

                  <div class="row cuadro-sm card-cita p-3">
                    <div class="col-md-10">
                      <div class="row justify-content-between pb-3">
                        <div class="col-md-4 n-cita">
                          <span><strong>Cita - 02135</strong></span>
                          <div class="espaciado"></div>
                          <div class="col-md-12">
                            <img
                              src="~/assets/anya-taylor-joy-getty1-t.jpg"
                              alt=""
                            />
                            <span class="ms-3">Anya Taylor</span>
                          </div>
                        </div>
                        <div class="col-md-4">
                          <span>Hora Prevista:</span> 07:30 am
                          <div class="espaciado"></div>
                          <span>Vacuna:</span> Pfizer
                        </div>
                        <div class="col-md-4">
                          <span>Hora Prevista:</span> 07:30 am
                          <div class="espaciado"></div>
                          <span>Vacuna:</span> Pfizer
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2">
                      <a href="#" class="btn btn-primary btn-sm">Completado</a>
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
      test: {},
    }
  },
  methods:{
      buscar()
      {
           axios
      .get('http://192.241.138.101:5560/api/Appointment/afiliado/'+this.search.text)
      .then((response) => (this.test = response.data))
      }
  },
  mounted() {
    axios
      .get('http://192.241.138.101:5560/api/Appointment/1/')
      .then((response) => (this.info = response.data))
  },
}
</script>