<template>
  <div id="computer">
    <div>
      <button>바위</button>
      <button>가위</button>
      <button>보</button>
    </div>
    <div>
      {{ result }}
    </div>
    <div>
      {{ score }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      result:'',
      score:0,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
