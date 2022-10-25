<template>
  <label>
    {{ label }}
    <input v-model="inputValue" />
  </label>

</template>

<script>
export default {
  name: 'input-value',
  props: {
    value: String,
    label: String
  },
  methods: function () {

  },
  computed: {
    inputValue: {
      get()
      {
        return this.value;
      },
      set(newValue)
      {
        return this.$emit('update:modelValue', newValue);
      }
    }
  }
}
</script>

<style scoped>
  input{
    display: block;
    margin: 20px;
  }
</style>
