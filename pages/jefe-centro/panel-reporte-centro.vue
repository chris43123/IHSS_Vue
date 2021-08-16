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
            <a href="#"><img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt=""></a>
          
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

                <div class="row formulario">
                    <div class="col-md-6">
                        <div class="row">
                        <div class="col-md-6">
                            <label for="#">Nombre Centro Médico:</label>
                            <input type="text" v-model="search.text" />
                            <button v-on:click="buscar()" class="btn btn-primary btn-sm mt-2">Buscar</button>
                        </div>
                        </div>
                    </div>
                </div>

                <div class="reporte mt-4 pt-4" v-if="!!info">
                    <div class="row">
                        <div class="col-md-6 logo">
                            <img src="~/assets/ihss.jpg" alt="">
                        </div>
                        <div class="col-md-6">
                            <div class="row dato-reporte">
                                <div class="col-md-4 dato"><span>Frecuencia: </span> Mensual</div>
                                <div class="col-md-4 dato"><span>No reporte: </span> 0245</div>
                                <div class="col-md-4 dato"><span>Emitido: </span> 12/04/2021</div>
                            </div>
                        </div>
                    </div>
                    <div class="row mt-4">
                        <h4>Reporte Individual de Centro Médico</h4>
                        <p>Datos correspondientes al 31 de diciembre de 2021</p>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-10">
                            <h5>{{info.nombre}}</h5>
                            <div class="row pt-3">
                                <div class="col-md-2 bold">
                                    <p>Ciudad:</p>
                                    <p>Horario:</p>
                                    <p>Director:</p>
                                </div>
                                <div class="col-md-3">
                                    <p class="t-gris">{{info.ciudad}}</p>
                                    <p class="t-gris">8:00 am - 7:30 pm</p>
                                    <p class="t-gris">{{info.nombreJefe}}</p>
                                </div>
                                <div class="col-md-2 bold">
                                    <p>Dirección:</p>
                                    <p>Categoría:</p>
                                    <p>No Colaboradores:</p>
                                </div>
                                <div class="col-md-4">
                                    <p class="t-gris">{{info.direccion}}</p>
                                    <p class="t-gris" v-if="info.tipo == 'C'">Clínica</p>
                                    <p class="t-gris" v-else-if="info.tipo == 'H'">Hospital</p>
                                    <p class="t-gris" v-else-if="info.tipo == 'A'">Centro de Adulto Mayor</p>
                                    <p class="t-gris">{{info.cantidadColab}}</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="row mt-4 estadistica">
                        <h5 class="pb-3">Personal de centro médico</h5>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">02</h1>
                                <h5 class="">M. General</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">14</h1>
                                <h5 class="">Enfermeras</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">02</h1>
                                <h5 class="">Cirujanos</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">5</h1>
                                <h5 class="">Laboratorio</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">1</h1>
                                <h5 class="">Epidemiólogo</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">2</h1>
                                <h5 class="">Otros</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-12 cuadro tabla-inventario">
                            <h4><strong>Resumen General de citas</strong></h4>
                            <table class="table table-hover">
                                <thead>
                                  <tr>
                                    <th scope="col">Vacuna</th>
                                    <th scope="col">Inventario</th>
                                    <th scope="col">Dañadas</th>
                                    <th scope="col">Aplicadas</th>
                                    <th scope="col">Reservadas</th>
                                  </tr>
                                </thead>
                                <tbody>
                                  <tr>
                                    <th scope="row">Moderna</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                  <tr>
                                    <th scope="row">Pfizer</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                  <tr>
                                    <th scope="row">Astrazeneca</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                  <tr>
                                    <th scope="row">Sputnik</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                  <tr>
                                    <th scope="row">Johnson</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                  <tr>
                                    <th scope="row">Dengvaxia</th>
                                    <td>1,250</td>
                                    <td class="t-red">121</td>
                                    <td>4,560</td>
                                    <td>652</td>
                                  </tr>
                                </tbody>
                              </table>
                        </div>   
                    </div>

                    <div class="row mt-4">
                        <h4>Estadística de flujo de citas por campaña</h4>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-3 cuadro-g me-3">
                            <div class="row pt-3">
                                <div class="col-md-12">
                                    <h6 class="t-blue">COVID-19</h6>
                                    <div class="separar"></div>
                                </div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Pfizer</strong></p></div>
                                <div class="col-md-6"><p class="text-end">650 <i class="fas fa-caret-up t-verde"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Moderna</strong></p></div>
                                <div class="col-md-6"><p class="text-end">40 <i class="fas fa-caret-down t-red"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Astrazeneca</strong></p></div>
                                <div class="col-md-6"><p class="text-end">250 <i class="fas fa-caret-up t-verde"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Sputnik</strong></p></div>
                                <div class="col-md-6"><p class="text-end">0 <i class="fas fa-caret-down t-red"></i></p></div>
                            </div>
                        </div>
                        <div class="col-md-3 cuadro-g me-3">
                            <div class="row pt-3">
                                <div class="col-md-12">
                                    <h6 class="t-blue">COVID-19</h6>
                                    <div class="separar"></div>
                                </div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Pfizer</strong></p></div>
                                <div class="col-md-6"><p class="text-end">650 <i class="fas fa-caret-up t-verde"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Moderna</strong></p></div>
                                <div class="col-md-6"><p class="text-end">40 <i class="fas fa-caret-down t-red"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Astrazeneca</strong></p></div>
                                <div class="col-md-6"><p class="text-end">250 <i class="fas fa-caret-up t-verde"></i></p></div>
                            </div>
                            <div class="row pb-3">
                                <div class="col-md-6"><p><strong>Sputnik</strong></p></div>
                                <div class="col-md-6"><p class="text-end">0 <i class="fas fa-caret-down t-red"></i></p></div>
                            </div>
                        </div>

                        <div class="row descargar">
                            <div class="col-md-12">
                                <a href="#" class="btn btn-primary btn-sm"><i class="fas fa-download"></i> Descargar</a>
                            </div>
                        </div>
                    </div>

                </div>

                <div class="row">
                    <div v-if="status==204" class="mt-3 col-md-4">
                        <div class="alert alert-warning alert-dismissible fade show" role="alert">
                                No hay resultados que coincidan con el criterio de búsqueda.
                            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>

    <script src="../js/dropdown.js"></script>
    <script src="https://kit.fontawesome.com/5883557ab1.js" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-U1DAWAznBHeqEIlVSCgzq+c9gqGAJn5c/t99JyeKa9xxaYpSvHU5awsuZVVFIhvj" crossorigin="anonymous"></script>
</div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      search: {},
      info: null,
      status: null,
    }
  },
  methods:{
      buscar()
      {
           axios
            .get('http://192.241.138.101:5560/api/Facilities/'+this.search.text)
            .then((response) => {this.info = response.data;
                this.status = response.status
            })
      }
  },
}
</script>