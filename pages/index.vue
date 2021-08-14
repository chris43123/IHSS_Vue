<template>
  <div v-if="info != 'undefined'" >
    <div v-for="aff in info" :key="aff.idAfiliado">
      <div class="card" >
        <img src="https://www.w3schools.com/howto/img_avatar2.png" alt="Avatar" style="width: 100%" />
        <div class="container">
          <h4><b>{{aff.nombre}}</b></h4>
          <p>{{aff.noIdentidad}}</p>
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
      info: null,
    }
  },
  mounted() {
    axios
      .get('http://192.241.138.101:5560/api/Affiliates')
      .then((response) => (this.info = response.data))
  },
}
</script>
