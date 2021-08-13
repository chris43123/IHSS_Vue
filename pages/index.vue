<template>
  <div v-if="info != undefinded">
    {{info.base_experience}}
  </div>
</template>

<script>
import axios from 'axios'
export default 
{
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://pokeapi.co/api/v2/pokemon/gengar')
      .then(response => (this.info = response.data))
  }
}
</script>
