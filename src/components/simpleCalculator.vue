<template>
  <div class="calculator">
    <h1>{{msg}}</h1>
    <div>
      <input type="number" placeholder="Type number here" v-model="inputNumber">
    </div>
    <div v-if="inputNumber !== ''">
      <input v-for="powValue in task1" :key="powValue.id"
       type="text" placeholder="Type number here" 
       :value="resultValue(powValue)" disabled>
    </div>
  </div>
</template>

<script>
export default {
  name: "simpleCalculator",
  data () {
    return {
      inputNumber: '',
      task1: [1,2,3,4,5],
    }
  },
  props: {
    msg: String
  },
  methods: {
    resultValue: function(powValue) {
      return `${this.inputNumber} ^ ${powValue} = ${Math.pow(this.inputNumber, powValue)}`;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  input {
    margin: 10px;
  }
</style>
