<template>
  <div :style="style" class="colourDisplay">
  </div>
</template>

<script>
export default {
  name: 'ColourDisplay',
  props: ['col', 'size'],
  computed: {
    style(){
      let result ='background-color: rgb('+this.col[0]+','+this.col[1]+','+this.col[2]+');'
      result += 'height:'+this.size+'%;'
      result += 'width:'+this.size+'%;'
      return result;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.colourDisplay{
  position: absolute;
  border-radius: 3%;
  border-top: 4px solid rgba(255,255,255,0.3);
  border-left: 4px solid rgba(255,255,255,0.2);
  border-bottom: 4px solid rgba(0,0,0,0.25);
  border-right: 4px solid rgba(0,0,0,0.15);
  box-sizing: border-box;
  box-shadow: 1px 1px 5px 1px rgba(0,0,0,0.6);
  background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0.3), rgba(0, 0, 0, 0.3));
}
</style>
