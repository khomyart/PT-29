<template>
  <div class="calculator">
    <h1>{{msg}}</h1>
    <div>
      <input type="number" placeholder="Type number here" v-model="inputNumber">
      <input type="number" placeholder="Type degree here" v-model="degreeOfNumber">
    </div>
    <div >
      <input v-for="powValue in task2" :key="powValue.id"
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
      degreeOfNumber: '',
      task2: [],
    }
  },
  props: {
    msg: String
  },
  watch: {
    degreeOfNumber: function() {
        this.task2 = [];
      for (let i = 0; i<this.degreeOfNumber; i++) {
        this.task2.push(i+1);
      }
    },
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
