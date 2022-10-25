<template>
  <button @click="getResult">GO</button>
  <p v-if="message">{{ message }}</p>
  <div v-if="(+resultValue) > 0 && (+resultValue) < 100 && resultValue !== 'NaN' && buttonClick">
    <p>{{ resultValue }}</p>
  </div>

</template>

<script>

export default {
  name: "result",
  props: {
    resultValue: String,
    weightValue: String,
    heightValue: String,
    buttonClick: Boolean
  },
  data() {
    return {
      message: ""
    }
  },
  methods: {
    check() {
      if (typeof(+this.weightValue) !== 'number' && typeof(+this.heightValue) !== 'number') {
        console.log(typeof(+this.weightValue));
        console.log(typeof(+this.heightValue));
        this.message = "Enter correct weight and height";
        return false;
      } else if (typeof(+this.weightValue) !== 'number') {
        this.message = "Enter correct weight";
        return false;
      } else if (typeof(+this.heightValue) !== 'number') {
        this.message = "Enter correct height";
        return false;
      } else if (+this.heightValue >= 3 || +this.heightValue <= 0.5) {
        this.message = "You are very unusual person";
        return false;
      } else if (+this.weightValue >= 500 || +this.weightValue <= 2) {
        this.message = "You are very unusual person";
        return false;
      } else {
        return true;
      }
    },
    getResult() {
      if (this.check()) {
        this.message = '';
        this.$emit('calculate-index');
      }
    }
  },
}

</script>

<style scoped>

</style>
