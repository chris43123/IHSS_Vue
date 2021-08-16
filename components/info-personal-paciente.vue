<template>

    <div class="row info-paciente mt-4">
        <div class="col-md-3 imagen">
        <img src="~/assets/anya-taylor-joy-getty1-t.jpg" alt="" />
        </div>
        <div class="col-md-4">
        <h5>Información Personal</h5>
        <div class="row pt-3">
            <div class="col-md-6 bold">
            <p>Nombre:</p>
            <p>Apellidos:</p>
            <p>Fecha de Nacimiento:</p>
            <p>Nacionalidad:</p>
            <p>Sexo:</p>
            <p>Dirección:</p>
            <p>Identidad:</p>
            </div>
            <div class="col-md-6">
            <p class="t-gris">{{nombre}}</p>
            <p class="t-gris">{{apellidos}}</p>
            <p class="t-gris">{{toDate(fechaNacimiento)}}</p>
            <p class="t-gris">{{nacionalidad}}</p>
            <p class="t-gris">{{sexo}}</p>
            <p class="t-gris">{{direccion}}</p>
            <p class="t-gris">{{noIdentidad}}</p>
            </div>
        </div>
        </div>
        <div class="col-md-4">
        <h5>Información Adicional</h5>
        <div class="row pt-3">
            <div class="col-md-6 bold">
            <p>Número Seguro:</p>
            <p>Fecha de Afiliación:</p>
            <p>Empresa:</p>
            </div>
            <div class="col-md-6">
            <p class="t-gris">{{idAfiliado}}</p>
            <p class="t-gris">{{toDate(fechaAfiliacion)}}</p>
            <p class="t-gris">{{empresa}}</p>
            </div>
        </div>
        </div>
        <div class="col-md-4"></div>
    </div>
</template>

<script>
export default {
    name: 'info-personal-paciente',
    props: [
        'idAfiliado',
        'nombre',
        'apellidos',
        'fechaNacimiento',
        'nacionalidad',
        'sexo',
        'direccion',
        'noIdentidad',
        'fechaAfiliacion',
        'empresa'
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