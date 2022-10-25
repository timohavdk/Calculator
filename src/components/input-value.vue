<template>
  <input @onUpdate:modelValue="logValue" v-model="index" />
</template>

<script>
export default {
  name: 'input-value',
  props: {
    index: String,
  },
  methods: function () {
    logValue()
    {
      console.log(this.index);
    }
  },
}
</script>

<style scoped>
  input{
    display: block;
    margin: 20px;
  }
</style>
