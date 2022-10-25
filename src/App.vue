<template @calculate-index="getResult" >
  <div class="wrapper">
    <h1>FitCal</h1>
    <input-value
        :label="weightLabel"
        :value="weight"
        v-model="weight"
    />
    <input-value
        :label="heightLabel"
        :value="height"
        v-model="height"
    />
    <result
        @calculate-index="turn"
        :resultValue="result"
        :weightValue="weight"
        :heightValue="height"
        :buttonClick="flag"
    />
  </div>

</template>

<script>
import InputValue from "@/components/input-value";
import Result from "@/components/result";

export default {
  name: 'App',
  components: {
    Result,
    InputValue,
  },
  emits: [
    'calculate-index',
  ],
  data() {
    return {
      weight: '0',
      height: '0',
      result: '0',
      weightLabel: 'Weight',
      heightLabel: 'Height',
      flag: false,
    }
  },
  methods: {
    turn() {
      this.flag = true;
      this.calculate();
    },
  },
  computed: {
    calculate() {
      let numberResult = (+this.weight / ((+this.height) ** 2)).toFixed(2);
      this.result = numberResult;
      console.log(this.result);
    }
  },
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
