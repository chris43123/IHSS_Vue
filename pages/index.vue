<template>

  <div class="container-fluid">
    <div class="row d-flex justify-content-center">
      <div class="col-md-4">
        <div class="vertical">
          <div class="form">
            <form
              id="app"
              @submit="checkForm"
              action="personal/inicio"
              method="post"
            >


            <div class="row d-flex justify-content-center pt-4 pb-4">
              <div class="col-md-8">
                <img src="~/assets/ihss.jpg" alt="">
              </div>
            </div>
            <div class="row">
              <div class="col-md-12">
                <h2 class="text-center t-gris">Login</h2>
              </div>
            </div>

            <div class="row" v-if="errors.length">
              <div class="col-12">
                <p v-if="errors.length">
                  <div v-for="error in errors" :key="error" class="alert alert-warning" role="alert">
                    {{ error }}
                  </div>
              </div>
            </div>

            <div class="row">
              <div class="col-md-12">
                <label for="">Usuario:</label>
                <input type="text" v-model="datos.usuario">
              </div>
            </div>
            <div class="row">
              <div class="col-md-12">
                <label for="">Contraseña:</label>
                <input type="password"  v-model="datos.contraseña">
              </div>
            </div>
            <div class="row mt-4">
              <div class="col-md-12  d-flex justify-content-center">
                <input type="submit" class="btn btn-primary" value="Iniciar sesión">
              </div>
            </div>

            <div class="row mt-3">
              <div class="col-md-12  d-flex justify-content-center">
                <a href="#" class="comentario t-blue">¿Olvidaste tu Contraseña?</a>
              </div>
            </div>
            </form>
          </div>
        </div>
      </div>
    </div>

  </div>
  
</template>

<script>
import axios from 'axios'
export default {
  data(){
    return {
      datos: {},
      errors: [],
    }
  },
  methods:{
    checkForm: function (e) {
      if (this.datos.contraseña == "1234" && this.datos.usuario == "Dalton") {
        return true;
      }

      this.errors = [];

      if (!this.datos.usuario) {
        this.errors.push('Por favor ingrese el nombre de usuario.');
      }
      if (!this.datos.contraseña) {
        this.errors.push('Por favor ingrese la contraseña.');
      }
      if (this.datos.contraseña != "1234" || this.datos.usuario != "Dalton") {
        this.errors.push('Usuario o contraseña incorrecta');
      }

      e.preventDefault();
    }
  }
}
</script>

<style>

.container-fluid {
  background: #F6F8F9;
  height: 1000vh;
}

.vertical {
  height: 100vh;
  display: flex;
  align-items: center;
}

.form {
  padding: 30px 35px;
  width: 100%;
  height: auto;
  box-shadow: 1px 1px 3px 0px rgba(210,210,210,0.75);
  -webkit-box-shadow: 1px 1px 3px 0px rgba(210,210,210,0.75);
  -moz-box-shadow: 1px 1px 3px 0px rgba(210,210,210,0.75);
  border-radius: 10px;
  background: #fff;
  border-top: 15px solid #109CF1;
}

label {
  padding: 15px 0;
  font-weight: 400;
  color: #5B6871;
}

input {
  width: 100%;
  padding: 5px;
  background: #F6F8F9;
  border: none;
  border-radius: 5px;
}

img {
  width: 100%;
  border-radius: 5px;
}
</style>