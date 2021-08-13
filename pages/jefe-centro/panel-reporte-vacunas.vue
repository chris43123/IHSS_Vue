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
            <div class="col-md-2 sidebar">
                <div class="row clinica">
                    <div class="col-md-3">
                        <i class="far fa-hospital"></i>
                    </div>
                    <div class="col-md-9">
                        <h4>Clínica</h4>
                        <p>Clínica Peiférica Calpules</p>
                    </div>
                </div>
                <div class="row items">
                    <a href="panel-inicio.html" class="active"><i class="fas fa-home"></i><span>Inicio</span> </a>
                    <a href="panel-citas.html"><i class="fas fa-clipboard-check"></i><span>Citas</span></a>

                    <button class="dropdown-btn">Reportes
                        <i class="fa fa-caret-down"></i>
                    </button>
                    <div class="dropdown-container">
                        <a href="panel-reporte-centro.html"><i class="far fa-hospital"></i><span>Reporte Centro Médico</span></a>
                        <a href=""><i class="fas fa-syringe"></i><span>Reporte Vacunas</span></a>
                        <a href=""><i class="fas fa-file-signature"></i><span>Reporte Citas</span></a>
                        <a href=""><i class="far fa-id-badge"></i><span>Reporte Pacientes</span> </a>
                    </div>

                    <div class="separar"></div>
                    
                    <button class="dropdown-btn">Nuevo Formulario
                        <i class="fa fa-caret-down"></i>
                    </button>
                    <div class="dropdown-container">
                        <a href="panel-form-pedido.html"><i class="fab fa-buffer"></i><span>Pedido</span> </a>
                        <a href="panel-form-dañadas.html"><i class="far fa-file-excel"></i><span>Dañadas</span> </a>
                    </div>
                </div>
            </div>

            <div class="col-md-10 panel">
                <div class="row justify-content-between top">
                    <div class="col-md-6 breadcumbs">
                        <span class="float-left">Inicio</span>
                    </div>
                    <div class="col-md-6 right">
                        <a href="#" class="btn btn-primary btn-sm">Encuesta</a>
                    </div>
                </div>

                <div class="reporte pt-4">
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
                                <h5><strong>Pfizer</strong></h5>
                                <div class="col-md-2 bold">
                                    <p>Proveedor:</p>
                                    <p>No de dosis:</p>
                                    <p>Código:</p>
                                </div>
                                <div class="col-md-2">
                                    <p class="t-gris">Biontech</p>
                                    <p class="t-gris">2</p>
                                    <p class="t-gris">012</p>
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
                                            <p class="t-gris">0.5 cc</p>
                                        </div>
                                        <div class="col-md-3 bold">
                                            <p>Precio de compra:</p>
                                            <p>Periodo de conservación:</p>
                                        </div>
                                        <div class="col-md-3">
                                            <p class="t-gris">12 euros</p>
                                            <p class="t-gris">30 días</p>
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
                            <p>Según el SAGE, la vacuna de ARN mensajero contra la COVID-19 de Pfizer-BioNTech es segura y eficaz. Con todo, hay grupos de población 
                                para los que no se recomienda la vacunación, ya sea debido a contraindicaciones, falta de suministros o falta de datos. Actualmente 
                                esos grupos los constituyen las personas con antecedentes de alergias graves, la mayoría de las mujeres embarazadas, viajeros 
                                internacionales que no forman parte de un grupo prioritario y menores de 16 años.

                                Antes de inmunizar a la población en general, la prioridad es comenzar a vacunar a los trabajadores sanitarios con alto riesgo de
                                exposición y, a continuación, a las personas mayores.
                            </p>
                            <p>Por lo general, la OMS no emite recomendaciones específicas sobre cada vacuna, sino sobre el conjunto de todas ellas para una enfermedad, 
                                a menos que las pruebas parezcan indicar que se requiere aplicar un planteamiento diferente. Debido a la gran variedad de vacunas contra 
                                la COVID-19 obtenidas en plataformas tecnológicas muy diferentes, la OMS está examinando vacunas autorizadas por organismos nacionales de 
                                reglamentación altamente competentes que estén disponibles en cantidades suficientes para atender las necesidades de muchos países. 
                                La OMS no tiene ninguna preferencia por ningún producto, y la variedad de estos, con sus atributos específicos y requisitos de 
                                manipulación, permite a los países encontrar aquellos más adecuados en función de sus circunstancias.
                            </p>
                            <a href="#" class="t-blue">Ver detalles <i class="far fa-plus-square"></i></a>
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
export default {

}
</script>