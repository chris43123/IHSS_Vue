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
                        <h4>Nuevo Pedido de Vacunas</h4>
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
                                    <label for="#">Campaña</label>
                                    <select name="" id="" required>
                                        <option value="">Seleccione--</option>
                                        <option value="">COVID-19</option>
                                        <option value="">Dengue</option>
                                        <option value="">Cordyceps</option>
                                    </select>
                                    <a href="#" class="btn btn-primary btn-sm mt-2">Buscar</a>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Vacuna</label>
                                    <select name="" id="" required>
                                        <option value="">Seleccione--</option>
                                        <option value="">Pfizer</option>
                                        <option value="">Moderna</option>
                                        <option value="">Astrazeneca</option>
                                    </select>
                                </div>
                                <div class="col-md-6">
                                    <label for="#">Cantidad</label>
                                    <input type="number" min="1" required>
                                    <p class="comentario">Basado en la información del reporte de inventario.</p>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-md-6">
                                    <label for="#">Fecha de pedido</label>
                                    <input type="date" name="" id="" required>
                                </div>
                                <div class="col-md-6">
                                    <label for="#">Fecha de entrega</label>
                                    <input type="date" name="" id="" required>
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