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
        <a href="#"
          ><img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt=""
        /></a>
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
            <a href="panel-inicio" class="active"
              ><i class="fas fa-home"></i><span>Inicio</span>
            </a>
            <button class="dropdown-btn">
              Nuevo Formulario
              <i class="fa fa-caret-down"></i>
            </button>
            <div class="dropdown-container">
              <a href="panel-form-centro"
                ><i class="fas fa-file-medical-alt"></i
                ><span>Centro Médico</span></a
              >
              <a href="panel-form-campaña"
                ><i class="fas fa-cubes"></i><span>Campaña</span></a
              >
              <a href="#"><i class="fas fa-user"></i><span>Informe</span></a>
            </div>

            <div class="separar"></div>

            <a href="#"
              ><i class="fas fa-file-medical-alt"></i
              ><span>Reporte Médico</span></a
            >
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
              <h4>Agregar Centro Médico</h4>
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
                    <label for="#">Centro médico</label>
                    <select name="" id="" required v-model="model.centro">
                      <option value="-1">Seleccione--</option>
                      <option value="1">Clínica Calpules</option>
                      <option value="2">Clínica Periférica</option>
                      <option value="3">Clínica Tegucigalpa</option>
                    </select>
                    <a href="#" class="btn btn-primary btn-sm mt-2">Buscar</a>
                  </div>
                </div>
                <div v-if="model.centro > 0">
                  <div class="row">
                    <div class="col-md-12">
                      <div class="cuadro-gris mt-4">
                        <h6><strong>Información - Clínica Calpules</strong></h6>
                        <div class="row pt-3">
                          <div class="col-md-3">
                            <p>Ciudad:</p>
                            <p>Dirección:</p>
                            <p>No. de colaboradores:</p>
                          </div>
                          <div class="col-md-3">
                            <p class="t-gris">San Pedro Sula</p>
                            <p class="t-gris">Col. Calpules</p>
                            <p class="t-gris">22</p>
                          </div>
                          <div class="col-md-3">
                            <p>Jefe de Centro:</p>
                            <p>Código:</p>
                          </div>
                          <div class="col-md-3">
                            <p class="t-gris">Marvin Coto</p>
                            <p class="t-gris">12</p>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="row">
                    <div class="col-md-6">
                      <label for="#">Campaña</label>
                      <select name="" id="" required>
                        <option value="">Seleccione--</option>
                        <option value="">Clínica Calpules</option>
                        <option value="">Clínica Periférica</option>
                        <option value="">Clínica Tegucigalpa</option>
                      </select>
                    </div>
                  </div>
                  <div class="row checkbox">
                    <div class="col-md-6">
                      <input type="checkbox" />
                      <label for="#">Cadena de frío</label>
                      <p class="comentario">
                        Marque esta opción en el caso de que el centro médico
                        disponga de una cadena de frío.
                      </p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12">
                      <label for="#">Comentario</label>
                      <textarea name="" id=""></textarea>
                      <p class="comentario">
                        Información adicional que se quiera aportar.
                      </p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12">
                      <input type="submit" value="Enviar" />
                    </div>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>

    <script src="../js/dropdown.js"></script>
    <script
      src="https://kit.fontawesome.com/5883557ab1.js"
      crossorigin="anonymous"
    ></script>
  </div>
</template>

<script>
export default {
  data() {
    return {
      model: {},
    }
  },
}
</script>