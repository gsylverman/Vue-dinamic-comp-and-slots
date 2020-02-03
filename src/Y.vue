<template>
  <div>
    Y
    <p>{{ nr }}</p>
    <button v-on:click="nr++">+</button>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      nr: 0
    };
  },
  beforeDestroy() {
    console.log("y before destroy");
  },
  destroyed() {
    console.log("Y destroied");
  }
};
</script>
