<template>
  <div class="container-fluid bg-white">
    <div class="row d-flex justify-content-center">
      <div class="col-md-4">
        <h2 class="text-center p-4 fw-bold">Formulario Cita de Vacuna</h2>
      </div>
    </div>
    <div class="row logo-cita d-flex justify-content-center">
      <div class="col-md-3">
        <img src="~/assets/ihss.jpg" alt="" />
      </div>
    </div>

    <div
      class="row formulario d-flex justify-content-center pt-5"
      v-if="pagina == 1"
    >
      <div class="col-md-4">
        <form action="#">
          <h5>Información Personal</h5>
          <div class="row">
            <div class="col-md-6">
              <label for="#">Nombre</label>
              <input type="text" v-model="cita.nombre" />
            </div>
            <div class="col-md-6">
              <label for="#">Apellidos</label>
              <input type="text" v-model="cita.apellidos" />
            </div>
          </div>
          <div class="row">
            <div class="col-md-6">
              <label for="#">Fecha Nacimiento</label>
              <input type="date" v-model="cita.fechaNacimiento" />
            </div>
            <div class="col-md-3">
              <label for="#">Sexo</label>
              <input type="radio" v-model="cita.sexo" value="F"/>
              <label class="l-check" for="#">Femenino</label>
            </div>
            <div class="col-md-3">
              <label for="#">-</label>
              <input type="radio" v-model="cita.sexo" value="M"/>
              <label class="l-check" for="#">Masculino</label>
            </div>
          </div>
          <div class="row">
            <div class="col-md-6">
              <label for="#">No. identidad</label>
              <input type="text" v-model="cita.identidad" />
            </div>
            <div class="col-md-6">
              <label for="#">Nacionalidad</label>
              <input type="text" v-model="cita.nacionalidad" />
            </div>
          </div>

          <div class="row pt-4">
            <div class="col">
              <h5>Información Adicional</h5>
            </div>
          </div>

          <div class="row">
            <div class="col-md-6">
              <label for="#">Ciudad</label>
              <select v-model="cita.ciudad">
                <option value="null">Seleccione--</option>
                <option value="San Pedro Sula">San Pedro Sula</option>
                <option value="Tegucigalpa">Tegucigalpa</option>
                <option value="Santa Rosa de Copán">Santa Rosa de Copán</option>
              </select>
            </div>
            <div class="col-md-6">
              <label for="#">Dirección</label>
              <input type="text" v-model="cita.direccion" />
              <p class="comentario">
                Indique bloque o número de casa y de ser posible una referencia.
              </p>
            </div>
          </div>
          <div class="row">
            <div class="col-md-6">
              <label for="#">Telefono</label>
              <input type="number" v-model="cita.telefono" />
            </div>
            <div class="col-md-6">
              <label for="#">Correo</label>
              <input type="email" v-model="cita.correo" />
            </div>
          </div>
        </form>
      </div>
    </div>

    <div
      class="row formulario d-flex justify-content-center pt-5"
      v-if="pagina == 2"
    >
      <div class="col-md-4">
        <form action="#">
          <h5>Información Personal</h5>
          <div class="row">
            <div class="col-md-6">
              <label for="#">Fecha primera dosis</label>
              <input type="date" v-model="cita.fechaPrimeraDosis" />
            </div>
            <div class="col-md-6">
              <label for="#">Centro Médico</label>
              <select v-model="cita.idCentroMed">
                <option value="-1">Seleccione--</option>
                <option value="3">Clínica Periferica Tepeaca</option>
                <option value="4">IHSS San Pedro Sula</option>
                <option value="5">Centro de rehabilitaciónt "Orquídea Blanca"</option>
                <option value="6">Centro de Salud Calpules</option>
              </select>
            </div>
          </div>

          <div class="row mt-4">
            <div class="col-md-12">
              <iframe
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4984.98724078592!2d-88.0141668488406!3d15.54077214582356!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f665ad438135a71%3A0xeaa8b2e923107752!2sInstituto%20Hondure%C3%B1o%20de%20Seguridad%20Social!5e0!3m2!1ses!2shn!4v1629078553074!5m2!1ses!2shn"
                style="border: 0"
                allowfullscreen=""
                loading="lazy"
              ></iframe>
            </div>
          </div>
        </form>
      </div>
    </div>

    <div v-if="pagina == 3">
      <div class="row d-flex justify-content-center pt-5">
        <div class="col-md-8">
          <div class="citas" v-if="cita != 'undefined'">
            <h6><strong>Información de Cita</strong></h6>
            <info-cita
              :idCita="'--'"
              :nombre="cita.nombre"
              :centroMedico="centros.find(x=>x.id==cita.idCentroMed).nombre"
              :fecha="cita.fechaPrimeraDosis"
              :aplicada="cita.aplicada"
              :vacuna="'Moderna'"
            />
          </div>
        </div>
      </div>
      <div class="row mt-4 d-flex justify-content-center">
        <div class="col-md-8">
          <h6>Ubicación</h6>
          <iframe
            :src="centros.find(x=>x.id==cita.idCentroMed).frame"
            style="border: 0"
            allowfullscreen=""
            loading="lazy"
          ></iframe>
        </div>
      </div>
    </div>

    <div class="row pb-4 d-flex justify-content-center pt-2">
        <div class="col-md-4">
            <div class="row d-flex justify-content-left">
                <div class="col-md-6">
                    <button v-if="pagina>1" class="btn btn-primary" v-on:click="pagina=pagina-1">Atras</button>
                    <button v-if="pagina<3" class="btn btn-primary" v-on:click="pagina=pagina+1">Siguiente</button>
                    <button v-if="pagina==3" class="btn btn-primary" v-on:click="enviar()">Enviar</button>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
     data() {
        return {
            cita: {},
            pagina: 1,
            centros: [
              {
                id: 3,
                nombre: 'IHSS Clinica Periferica Tepeaca',
                frame: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4984.98724078592!2d-88.0141668488406!3d15.54077214582356!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f665ad438135a71%3A0xeaa8b2e923107752!2sInstituto%20Hondure%C3%B1o%20de%20Seguridad%20Social!5e0!3m2!1ses!2shn!4v1629078553074!5m2!1ses!2shn'
              },
              {
                id: 4,
                nombre: 'IHSS San Pedro Sula',
                frame: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4984.98724078592!2d-88.0141668488406!3d15.54077214582356!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f665ad438135a71%3A0xeaa8b2e923107752!2sInstituto%20Hondure%C3%B1o%20de%20Seguridad%20Social!5e0!3m2!1ses!2shn!4v1629078553074!5m2!1ses!2shn'
              },
              {
                id: 5,
                nombre: 'Centro de rehabilitación Orquídea Blanca',
                frame: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4984.98724078592!2d-88.0141668488406!3d15.54077214582356!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f665ad438135a71%3A0xeaa8b2e923107752!2sInstituto%20Hondure%C3%B1o%20de%20Seguridad%20Social!5e0!3m2!1ses!2shn!4v1629078553074!5m2!1ses!2shn'
              },
              {
                id: 6,
                nombre: 'Centro de Salud Calpules',
                frame: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4984.98724078592!2d-88.0141668488406!3d15.54077214582356!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f665ad438135a71%3A0xeaa8b2e923107752!2sInstituto%20Hondure%C3%B1o%20de%20Seguridad%20Social!5e0!3m2!1ses!2shn!4v1629078553074!5m2!1ses!2shn'
              }
            ]
        }
    },
    methods:{
        enviar(){
            axios
                .post('http://192.241.138.101:5560/api/Appointment', this.cita)
        }
    }

}
</script>