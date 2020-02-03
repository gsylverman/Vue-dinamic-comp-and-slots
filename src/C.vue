<template>
  <div>
    <div>C</div>
    <div>NR: {{nr}}</div>
    <button v-on:click="nr++">+</button>
  </div>
</template>

<script>
export default {
    created(){
        console.log("created");
    },
    beforeDestroy(){
        console.log("beforeDestroy");
    },
    destroyed(){
        console.log("destroyed")
    },
    beforeCreate(){
        console.log("before create")
    },
    activated(){
        console.log("activated")
    },
    deactivated(){
        console.log("deactivated");
    },
  data:()=>{
      return {
          nr:0
      }
  }
};
</script>

<style scoped></style>
