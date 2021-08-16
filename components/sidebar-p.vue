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
            <a href="panel-form-cita"><i class="far fa-id-badge"></i><span>Estado Cita</span> </a>

            <div class="separar"></div>

            <button class="dropdown-btn">Reportes
                <i class="fa fa-caret-down"></i>
            </button>
            <div class="dropdown-container">
                <a href="panel-reporte-paciente"><i class="far fa-id-badge"></i><span>Reporte Pacientes</span> </a>
                <a href="panel-reporte-cita"><i class="fas fa-file-signature"></i><span>Reporte Citas</span></a>
            </div>
            
        </div>
    </div>
</template>


<script>
export default {

}
</script>