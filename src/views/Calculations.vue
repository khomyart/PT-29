<template>
  <div class="calculations">
    <img alt="Vue logo" src="../assets/logo.png" />
    <simpleCalculator msg="Simple calculator "/>
    <extendedCalculator msg="Extended calculator "/>
  </div>
</template>

<script>
// @ is an alias to /src
import simpleCalculator from "@/components/simpleCalculator.vue";
import extendedCalculator from "@/components/extendedCalculator.vue"

export default {
  name: "Calculations",
  components: {
    simpleCalculator,
    extendedCalculator
  }
};
</script>
