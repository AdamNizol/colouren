<template>
  <div class="colourGen">
    <button @click="generateColours">Generate</button>
    <div class="colourDisplayContainer">
      <ColourDisplay size="100" :col="primary"/>
      <ColourDisplay size="55" :col="secondary" />
    </div>
  </div>
</template>

<script>
import ColourDisplay from './ColourDisplay.vue'

export default {
  name: 'ColourGen',
  components: {
    ColourDisplay
  },
  data(){
    return {
      primary: [255,0,0],
      secondary: [0,255,0]
    }
  },
  methods: {
    generateColours(){
      this.primary = this.generateColour();
      this.secondary = this.generateColour();
    },
    generateColour(){
      let minCol = 50;
      let maxCol = 255;

      let result = []
      for(let i = 0; i < 3; i++){
        result.push(minCol+ Math.floor(Math.random()*(maxCol-minCol)))
      }

      return result;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.colourGen{
  display: flex;
  flex-direction: column;
  align-items: center;
}
.colourDisplayContainer{
  width: 15em;
  height: 15em;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
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
}
</style>
