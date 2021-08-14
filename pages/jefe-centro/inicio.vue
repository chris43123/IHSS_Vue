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
            
            <sidebar/>

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
                    <div class="col-md-11 cuadro resumen">
                        <h4>Resumen General de citas</h4>
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

                <div class="row pt-3">
                    <div class="col-md-11 cuadro tabla-inventario">
                        <h4>Inventario de Vacunas</h4>
                        <table class="table table-hover">
                            <thead>
                              <tr>
                                <th scope="col">Vacuna</th>
                                <th scope="col">Inventario</th>
                                <th scope="col">Dañadas</th>
                                <th scope="col">Aplicadas</th>
                                <th scope="col">Reservadas</th>
                              </tr>
                            </thead>
                            <tbody>
                              <tr>
                                <th scope="row">Moderna</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                              <tr>
                                <th scope="row">Pfizer</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                              <tr>
                                <th scope="row">Astrazeneca</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                              <tr>
                                <th scope="row">Sputnik</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                              <tr>
                                <th scope="row">Johnson</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                              <tr>
                                <th scope="row">Dengvaxia</th>
                                <td>1,250</td>
                                <td class="t-red">121</td>
                                <td>4,560</td>
                                <td>652</td>
                              </tr>
                            </tbody>
                          </table>
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

// import sidebar from '@/components/sidebar.vue'

export default {

}
</script>Sidebar