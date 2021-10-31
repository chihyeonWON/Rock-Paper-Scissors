<template>
<div>
  <div id="computer" :style="computedStyleObject">
  </div>
    <div>
      <button @onclick = "onClickButton('바위')">바위</button>
      <button @onclick = "onClickButton('가위')">가위</button>
      <button @onclick = "onClickButton('보')">보</button>
    </div>
    <div>
      {{ result }}
    </div>
    <div>
      현재 {{ score }}점
    </div>
</div>
</template>

<script>
  const rspCoords = {
    바위:'0',
    가위:'-142px',
    보:'-284px'
  };
  let interval = null;
  export default {
    name: 'App',
    components: {
    },
    data(){
      return{
        imgCoord: rspCoords.바위,
        result:'',
        score:0,
      }
    },
    computed:{
      computedStyleObject(){
        return {background: `url(https://en.pimg.jp/023/182/267/1/23182267.jpg) ${this.imgCoord} 0`}
      }
    },
    mounted(){
      interval = setInterval(() => {
        if(this.imgCoord === rspCoords.바위) {
          this.imgCoord = rspCoords.가위;
        } else if(this.imgCoord === rspCoords.가위) {
          this.imgCoord = rspCoords.보;
        } else if(this.imgCoord === rspCoords.보){
          this.imgCoord = rspCoords.바위;
        }
      }, 100);  
    },
    beforeUnMount(){
      clearInterval(interval);  
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

<style scoped>
  #computer {
    width: 142px;
    height: 200px;
    background-position: 0 0;
  }
</style>