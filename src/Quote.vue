<template>
  <div>
    <div>
      <slot name="title"></slot>
    </div>
    <div>
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
div {
  margin: 5px;
  text-align: center;
  box-shadow: 1px 1px 1px 1px grey;
  padding-bottom: 5px;
}
</style>
