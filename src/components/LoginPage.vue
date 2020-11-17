<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  props: {
    msg: String,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .btn{
    padding:5px;
    background-color: white;
    border-radius: 2px;
    border: 1px solid #999;
    cursor: pointer;
  }
</style>