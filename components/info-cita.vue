<template>

    <div class="row cuadro card-cita me-0">
        <p><strong class="t-blue">Información Dosis</strong></p>
        <div class="col-md-12">
            <div class="row justify-content-between">
                <div class="col-md-2 n-cita">
                    <span><strong>Cita - {{idCita}}</strong></span>
                    <div class="row mt-3 justify-content-between">
                        <div class="col-md-12">
                            <img
                            src="~/assets/anya-taylor-joy-getty1-t.jpg"
                            alt=""
                            />
                            <span class="ms-3">{{nombre}}</span>
                        </div>
                    </div>
                </div>
                <div class="col-md-2 bold">
                    <p>Centro Médico:</p>
                    <p>Ciudad:</p>
                </div>
                <div class="col-md-2">
                    <p class="t-gris">{{centroMedico}}</p>
                    <p class="t-gris">San Pedro Sula</p>
                </div>
                <div class="col-md-2 bold">
                    <p>Hora Prevista:</p>
                    <p>Vacuna:</p>
                </div>
                <div class="col-md-2">
                    <p class="t-gris">{{ toHours(fecha) }}</p>
                    <p class="t-gris">{{vacuna}}</p>
                </div>
                <div class="col-md-2">
                    <span class="btn btn-primary" v-if="aplicada">Completado</span>
                    <span class="btn btn-gray" v-else>Pendiente</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'info-cita',
    props: [
        'idCita',
        'nombre',
        'centroMedico',
        'fecha',
        'vacuna',
        'aplicada'
    ],
    methods: {
        toDate(date) {
        var your_date_object = new Date()
        your_date_object.setTime(Date.parse(date))

        var date = your_date_object.getDate()
        var month = your_date_object.getMonth()
        var year = your_date_object.getFullYear()
        return date+ '/' + month + '/' + year; 
        },
        toHours(date) {
        var your_date_object = new Date()
        your_date_object.setTime(Date.parse(date))

        var min = your_date_object.getMinutes()
        var hour = your_date_object.getHours()
        return (hour < 10 ? '0'+hour:hour) + ':' + (min<10 ? '0'+min:min) 
        },
    },
}
</script>