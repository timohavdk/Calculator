<template>
  <div>
    <p>{{ info }}</p>
  </div>
</template>

<script>
import axios from '../../node_modules/axios'

export default {
  name: "api-component",
  data() {
    return {
      info: null,
      array: [1, 2, 3, 4, 5]
    }
  },
  mounted() {
    axios
      .get('https://finalspaceapi.com/api/v0/character/?limit=2')
        .then(response => {
          this.info = response;
          console.log(response);
        })
  },
}
</script>

<style scoped>

</style>
