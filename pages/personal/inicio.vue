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
            
            <sidebar-p/>

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

                <div class="row pt-3">
                    <div class="col-md-8 cuadro resumen">
                        <h4><strong>Resumen General de citas</strong></h4>
                        <div class="row pt-3">
                            <div class="col-md-2 dato bl">
                                <h6>Total Citas</h6>
                                <h3><i class="fas fa-long-arrow-alt-down t-red"></i><strong class="ms-2">50</strong></h3>
                            </div>
                            <div class="col-md-2 dato bl">
                                <h6>Completadas</h6>
                                <h3><i class="fas fa-long-arrow-alt-up t-blue"></i><strong class="ms-2">12</strong></h3>
                            </div>
                            <div class="col-md-2 dato">
                                <h6>Pendientes</h6>
                                <h3><strong>38</strong></h3>
                            </div>
                            <div class="col-md-6 aux">
                                <i class="fas fa-circle t-red"></i><span class="ms-2">Incremento</span>
                                <i class="fas fa-circle t-blue"></i><span class="ms-2">Decremento</span>
                            </div>
                        </div>
                    </div>   
                </div>

                <div class="row citas">
                    <div class="col-md-6">
                        <div v-if="info != 'undefined'" >
                            <div v-for="aff in info" :key="aff.idAfiliado">
                                <div class="row cuadro-sm card-cita">
                                    <div class="col">
                                        <div class="row justify-content-between pb-2">
                                            <div class="col-md-4 n-cita">
                                                <span><strong>Cita - {{aff.idCita}}</strong></span>
                                            </div>
                                            <div class="col-md-4 text-center">
                                                <span>Hora:</span> {{aff.fecha}}
                                            </div>
                                            <div class="col-md-4 text-end">
                                                <span>Vacuna:</span> {{aff.idvacuna}}
                                            </div>
                                        </div>
                                        <div class="row justify-content-between">
                                            <div class="col-md-6">
                                                <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="">
                                                <span class="ms-3">{{aff.nombre}}</span>
                                            </div>
                                            <div class="col-md-6 text-end">
                                                <a href="#">Ver detalles</a>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
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
      info: null,
    }
  },
  mounted() {
    axios
      .get('http://192.241.138.101:5560/api/Appointment')
      .then((response) => (this.info = response.data))
  },
}
</script>