<template>
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
            <a href="inicio" class="active"><i class="fas fa-home"></i><span>Inicio</span> </a>
            <a href="panel-citas"><i class="fas fa-clipboard-check"></i><span>Citas</span></a>

            <button class="dropdown-btn">Reportes
                <i class="fa fa-caret-down"></i>
            </button>
            <div class="dropdown-container">
                <a href="panel-reporte-centro"><i class="far fa-hospital"></i><span>Reporte Centro Médico</span></a>
                <a href="panel-reporte-vacunas"><i class="fas fa-syringe"></i><span>Reporte Vacunas</span></a>
                <a href="panel-reporte-cita"><i class="fas fa-file-signature"></i><span>Reporte Citas</span></a>
                <a href="panel-reporte-paciente"><i class="far fa-id-badge"></i><span>Reporte Pacientes</span> </a>
            </div>

            <div class="separar"></div>
            
            <button class="dropdown-btn">Nuevo Formulario
                <i class="fa fa-caret-down"></i>
            </button>
            <div class="dropdown-container">
                <a href="panel-form-pedido"><i class="fab fa-buffer"></i><span>Pedido</span> </a>
                <a href="panel-form-dañadas"><i class="far fa-file-excel"></i><span>Dañadas</span> </a>
            </div>
        </div>
    </div>
</template>


<script>
export default {

}
</script>