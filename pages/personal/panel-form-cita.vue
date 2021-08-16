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

                <div class="row formulario">
                    <div class="col-md-6">
                        <div class="row">
                        <div class="col-md-6">
                            <label for="#">Afiliado:</label>
                            <input type="text"  pattern="[0-9]{5}" v-model="search.text" />
                            <button v-on:click="buscar()" class="btn btn-primary btn-sm mt-2">Buscar</button>
                        </div>
                        </div>
                    </div>
                </div>

                <div class="citas" v-if="citas != 'undefined'">
                    <h6><strong>Información de Cita</strong></h6>
                    <info-cita
                        v-for="cita of citas"
                        :key="cita.idCita"
                        :idCita="cita.idCita"
                        :nombre="cita.nombre"
                        :centroMedico="cita.centroMedico"
                        :fecha="cita.fecha"
                        :aplicada="cita.aplicada"
                        :vacuna="cita.vacuna"
                    />

                    <div class="row formulario">
                    <div class="col-md-6">
                        <div class="row">
                            <div class="col-md-12">
                                <label for="#">Comentario</label>
                                <textarea name=""></textarea>
                                <p class="comentario">Información adicional que se quiera aportar.</p>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-md-12">
                                <button class="btn btn-primary">Enviar</button>
                            </div>
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
</div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      search: {},
      citas: null,
      status: null
    }
  },
  methods:{
      buscar()
      {
        axios
          .get('http://192.241.138.101:5560/api/Appointment/afiliado/'+this.search.text)
          .then((response) => {this.citas = response.data;
                this.status = response.status
            })
      },
  },
}
</script>