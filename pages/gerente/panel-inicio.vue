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
                    <button class="dropdown-btn">Nuevo Formulario
                        <i class="fa fa-caret-down"></i>
                    </button>
                    <div class="dropdown-container">
                        <a href="panel-form-centro.html"><i class="fas fa-file-medical-alt"></i><span>Centro Médico</span></a>
                        <a href="panel-form-campaña.html"><i class="fas fa-cubes"></i><span>Campaña</span></a>
                        <a href="#"><i class="fas fa-user"></i><span>Informe</span></a>
                    </div>

                    <div class="separar"></div>

                    <a href="#"><i class="fas fa-file-medical-alt"></i><span>Reporte Médico</span></a>
                    <a href="#"><i class="fas fa-cubes"></i><span>Inventario</span></a>
                    <a href="#"><i class="fas fa-user"></i><span>Empleados</span></a>
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

              
                <div class="row mt-4 estadistica">
                    <h5 class="pb-3">Estadística General de Población Vacunada</h5>
                    <div class="col-md-11">
                        <div class="row">
                            <div class="col-md-3">
                                <div class="cuadro-gris dato">
                                    <h1>126,489</h1>
                                    <h6>Población Vacunada</h6>
                                    <a href="#">Ver detalles</a>
                                </div>
                            </div>
                            <div class="col-md-3">
                                <div class="cuadro-gris dato">
                                    <h1>126,489</h1>
                                    <h6>Población Vacunada</h6>
                                    <a href="#">Ver detalles</a>
                                </div>
                            </div>
                            <div class="col-md-3">
                                <div class="cuadro-gris dato">
                                    <h1>126,489</h1>
                                    <h6>Población Vacunada</h6>
                                    <a href="#">Ver detalles</a>
                                </div>
                            </div>
                            <div class="col-md-3">
                                <div class="cuadro-gris dato">
                                    <h1>126,489</h1>
                                    <h6>Población Vacunada</h6>
                                    <a href="#">Ver detalles</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="row grafico">
                    <div class="col-md-11">
                        <canvas id="myChart"></canvas>
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