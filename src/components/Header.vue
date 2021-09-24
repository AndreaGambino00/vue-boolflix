<template>
  <header>
    <h2>Boolflix</h2>
    <input type="text" v-model="query">
    <button @click="search">Search</button>
  </header>
   
</template>

<script>
export default {
  name: 'Header',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
    padding: 0;
}

h2 {
  color: red;
}

header {
  display: flex;
  justify-content: space-between;
  background-color: black;
  
  padding: 30px 0;
}

header input {
  padding: 3px;
  margin-left: 1100px;
}

header button {
  margin-left: 20px;
  padding: 3px 10px;
}
</style>
