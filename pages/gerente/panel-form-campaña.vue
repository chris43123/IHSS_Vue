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
                        <p>Clínica Periférica Calpules</p>
                    </div>
                </div>
                <div class="row items">
                    <a href="panel-inicio" class="active"><i class="fas fa-home"></i><span>Inicio</span> </a>    
                    <button class="dropdown-btn">Nuevo Formulario
                        <i class="fa fa-caret-down"></i>
                    </button>
                    <div class="dropdown-container">
                        <a href="panel-form-centro"><i class="fas fa-file-medical-alt"></i><span>Centro Médico</span></a>
                        <a href="panel-form-campaña"><i class="fas fa-cubes"></i><span>Campaña</span></a>
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
                        <h4>Nueva Campaña</h4>
                    </div>
                    <div class="col-md-6 right">
                        <h4>23, septiembre 2021</h4>
                    </div>
                </div>
                <div class="row formulario">
                    <p class="t-blue">Todos los campos son obligatorios.</p>
                    <div class="col-md-6">
                        <form action="#">
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Nombre de la campaña</label>
                                    <input type="text" name="" id="" required>
                                </div>
                                <div class="col-md-6">
                                    <label for="#">Aprobada por</label>
                                    <input type="text" name="" id="" required>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Fecha de inicio</label>
                                    <input type="date" required>
                                </div>
                                <div class="col-md-6">
                                    <label for="#">Fecha de finalización</label>
                                    <input type="date" required>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Vacunas aprobadas</label>
                                    <select name="" id="" required>
                                        <option value="">Seleccione--</option>
                                        <option value="">Pfizer</option>
                                        <option value="">Moderna</option>
                                        <option value="">Astrazeneca</option>
                                    </select>
                                    <a href="#" class="btn btn-primary btn-sm mt-2">Buscar</a>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <div class="cuadro-gris mt-2">
                                        <p>Pfizer</p>
                                        <p>Astrazeneca</p>
                                        <p>Moderna</p>
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Población Meta</label>
                                    <input type="number" required>
                                </div>
                                <div class="col-md-3">
                                    <label for="#">Edad mínima</label>
                                    <select name="" id="" required>
                                        <option value="">18-</option>
                                        <option value="">18-30</option>
                                        <option value="">30-50</option>
                                        <option value="">50-65</option>
                                        <option value="">65+</option>
                                    </select>
                                </div>
                                <div class="col-md-3">
                                    <label for="#">Edad máxima</label>
                                    <select name="" id="" required>
                                        <option value="">18-</option>
                                        <option value="">18-30</option>
                                        <option value="">30-50</option>
                                        <option value="">50-65</option>
                                        <option value="">65+</option>
                                    </select>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-12">
                                    <label class="pt-4">Enfermedades Base</label>
                                </div>
                            </div>
                            <div class="row checkbox">
                                <div class="col-md-6">
                                    <input type="checkbox">
                                    <label for="#">Enfermedad pulmonar obstructiva crónica (EPOC) </label>
                                </div>
                                <div class="col-md-6 ">
                                    <input type="checkbox">
                                    <label for="#">Cáncer de pulmón</label>
                                </div>
                            </div>
                            <div class="row checkbox">
                                <div class="col-md-6">
                                    <input type="checkbox">
                                    <label for="#">Fibrosis quística</label>
                                </div>
                                <div class="col-md-6 ">
                                    <input type="checkbox">
                                    <label for="#">Fibrosis pulmonar</label>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-12">
                                    <label for="#">Comentario</label>
                                    <textarea name="" id=""></textarea>
                                    <p class="comentario">Información adicional que se quiera aportar.</p>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-12">
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