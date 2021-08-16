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
                            <label for="#">Código Vacuna:</label>
                            <input type="text" required v-model="search.text" />
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
                        <h4>Reporte Individual de Vacuna</h4>
                        <p>Datos correspondientes al 31 de diciembre de 2021</p>
                    </div>

                    <div class="row mt-2">
                        <div class="col-md-12">
                            <div class="row pt-3">
                                <h5><strong>{{info.nombre}}</strong></h5>
                                <div class="col-md-2 bold">
                                    <p>Proveedor:</p>
                                    <p>No de dosis:</p>
                                    <p>Código:</p>
                                </div>
                                <div class="col-md-2">
                                    <p class="t-gris">{{info.proveedor}}</p>
                                    <p class="t-gris">{{info.numeroDosis}}</p>
                                    <p class="t-gris">{{info.idVacuna}}</p>
                                </div>
                                <div class="col-md-7 cuadro-g ps-4">
                                    <div class="row">
                                        <p><strong>Características</strong></p>
                                        <div class="col-md-3 bold">
                                            <p>Porcentaje efectividad:</p>
                                            <p>Temperatura de conservación:</p>
                                            <p>Volúmen por dosis:</p>
                                        </div>
                                        <div class="col-md-3">
                                            <p class="t-gris">95%</p>
                                            <p class="t-gris">2 C - 8 C</p>
                                            <p class="t-gris">{{info.volumenDosis}}</p>
                                        </div>
                                        <div class="col-md-3 bold">
                                            <p>Precio de compra:</p>
                                            <p>Periodo de conservación:</p>
                                        </div>
                                        <div class="col-md-3">
                                            <p class="t-gris">12 euros</p>
                                            <p class="t-gris">{{info.periodoConservacion}} días</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-12">
                            <div class="row cuadro">
                                <h6 class="pb-3"><strong>Efectos Secundarios</strong></h6>
                                <div class="col-md-4">
                                    <div class="row checkbox">
                                        <div class="col-md-12 pb-3">
                                            <input type="checkbox" checked>
                                            <label for="#">Fiebre alta</label>
                                        </div>
                                        <div class="col-md-12  pb-3">
                                            <input type="checkbox">
                                            <label for="#">Dolores musculares</label>
                                        </div>
                                    </div>
                                </div>
                                <div class="col-md-4">
                                    <div class="row checkbox">
                                        <div class="col-md-12 pb-3">
                                            <input type="checkbox" checked>
                                            <label for="#">Cansancio-Fatiga</label>
                                        </div>
                                        <div class="col-md-12 pb-3">
                                            <input type="checkbox">
                                            <label for="#">Dolor de cabeza</label>
                                        </div>
                                    </div>
                                </div>
                                <div class="col-md-4 ">
                                    <div class="row checkbox">
                                        <div class="col-md-12 pb-3">
                                            <input type="checkbox">
                                            <label for="#">Pérdida del olfato</label>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-12 cuadro-g p-4">
                            <h6><strong>Información Adicional</strong></h6>
                            <p>{{info.informacion}}</p>
                            <a :href="info.url" class="t-blue">Ver detalles <i class="far fa-plus-square"></i></a>
                        </div>
                    </div>

                    <div class="row mt-4 estadistica">
                        <h6 class="pb-3"><strong>Estadísticas Generales</strong></h6>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-blue">8,500</h1>
                                <h5>Inventario</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1>1,500</h1>
                                <h5>Reservadas</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-verde">7,000</h1>
                                <h5>Disponibles</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-red">145</h1>
                                <h5>Dañadas</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="cuadro-g dato">
                                <h1 class="t-gris">645</h1>
                                <h5>En revisión</h5>
                                <a href="#">Ver detalles</a>
                            </div>
                        </div>
                    </div>

                    <div class="row mt-4">
                        <h6><strong>Distribución de insumos en los centros médicos</strong></h6>
                    </div>

                    <div class="row mt-4">
                        <div class="col-md-3 cuadro-g me-3">
                            <div class="row pt-3">
                                <div class="col-md-12">
                                    <h6 class="t-blue">Clínicas</h6>
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
                                    <h6 class="t-blue">Hospitales</h6>
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
                                    <h6 class="t-blue">Centros de Vacunación</h6>
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
                    </div>

                    <div class="row descargar">
                        <div class="col-md-12">
                            <a href="#" class="btn btn-primary btn-sm"><i class="fas fa-download"></i> Descargar</a>
                        </div>
                    </div>

                </div>
                
            </div>
        </div>
    </div>

    <script src="../js/dropdown.js"></script>
    <script src="https://kit.fontawesome.com/5883557ab1.js" crossorigin="anonymous"></script>
</div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      search: {},
      info: null,
    }
  },
  methods:{
      buscar()
      {
           axios
            .get('http://192.241.138.101:5560/api/Vaccine/'+this.search.text)
            .then((response) => (this.info = response.data))
      }
  },
}
</script>