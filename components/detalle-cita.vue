<template>

    <div class="row cuadro-g mt-2">
        <p><strong>Detalles Generales</strong></p>
        <div class="col-md-2 bold">
            <p>Afiliado:</p>
            <p>No de Afiliado:</p>
            <p>Centro Médico:</p>
        </div>
        <div class="col-md-3">
            <p class="t-gris">{{nombre}}</p>
            <p class="t-gris">{{idAfiliado}}</p>
            <p class="t-gris">{{centroMedico}}</p>
        </div>
        <div class="col-md-2 bold">
            <p>Vacuna:</p>
            <p>Fecha primera dosis:</p>
            <p>Fecha segunda dosis:</p>
        </div>
        <div class="col-md-3">
            <p class="t-gris">{{vacuna}}</p>
            <p class="t-gris">{{toDate(pfecha)}}</p>
            <p class="t-gris" v-if="!!sfecha">{{ toDate(sfecha) }}</p>
            <p class="t-gris" v-else>--</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'detalle-cita',
    props: [
        'nombre',
        'idAfiliado',
        'centroMedico',
        'pfecha',
        'sfecha',
        'vacuna',
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