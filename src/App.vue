<template>
  <div class="wrapper">
    <h1>FitCal</h1>
    <input-value
        :index="weight"
        v-model="weight"
    />
    <input-value
        :index="height"
        v-model="height"
    />
    <button-calculation

    />
    <result-output v-if="result"

    />
  </div>

</template>

<script>
import InputValue from "@/components/input-value";
import ButtonCalculation from "@/components/button-calculation";
import ResultOutput from "@/components/result-output";

export default {
  name: 'App',
  components: {
    ResultOutput,
    ButtonCalculation,
    InputValue,
  },
  data() {
    return {
      weight: '0',
      height: '0',
      result: '0',
    }
  }
}
</script>

<style>
h1 {
  text-align: center;
  color: lightskyblue;
  font-size: 64px;
  margin-top: 100px;
}
.wrapper{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
