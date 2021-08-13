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
                    <a href="#"><i class="fas fa-tasks"></i><span>Reportes</span></a>

                    <div class="separar"></div>
                    <a href="#"><i class="fas fa-clipboard-check"></i><span>Nueva Cita</span></a>
                    <a href="#"><i class="far fa-id-badge"></i><span>Pacientes Vacunados</span></a>
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

                <div class="row justify-content-between info">
                    <div class="col-md-6">
                        <h4>Hola, Valentina Flores</h4>
                    </div>
                    <div class="col-md-6 right">
                        <h4>23, septiembre 2021</h4>
                    </div>
                </div>

                <div class="citas">
                    <h6><strong>Información de Cita</strong></h6>
                    <div class="row cuadro card-cita me-0">
                        <p><strong  class="t-blue">Información Dosis - 1</strong></p>
                        <div class="col-md-12">
                            <div class="row justify-content-between">
                                <div class="col-md-2 n-cita">
                                    <span><strong>Cita - 02135</strong></span>
                                    <div class="row mt-3 justify-content-between">
                                        <div class="col-md-12">
                                            <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="">
                                            <span class="ms-3">Anya Taylor</span>
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

                <div class="row cuadro card-cita me-0">
                    <p><strong  class="t-blue">Información Dosis - 2</strong></p>
                    <div class="col-md-12">
                        <div class="row justify-content-between">
                            <div class="col-md-2 n-cita">
                                <span><strong>Cita - 02135</strong></span>
                                <div class="row mt-3 justify-content-between">
                                    <div class="col-md-12">
                                        <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="">
                                        <span class="ms-3">Anya Taylor</span>
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
                                <a href="#" class="btn btn-gray">Pendiente</a>
                            </div>
                        </div>
                        
                    </div>
                </div>

                <div class="formulario">
                    <form action="#">
                        <div class="row">
                            <div class="col-md-6">
                                <label for="#">Comentario</label>
                                <textarea name="" id=""></textarea>
                                <p class="comentario">Información adicional que se quiera aportar.</p>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-md-6">
                                <input type="submit" value="Enviar">
                            </div>
                        </div>
                    </form>
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