<template>
  <div class="progressbar">
    <div class="progressbar__progress" :style="this.styleObj" ></div>
    <div class="progressbar__bg"></div>
  </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: ['progress'],
  data() {
    return {
    }
  },
  setup() {
    
  },
  computed:{
    styleObj() {
      return {width: this.progress*2.75 + 'vw'};
    }
  }
}
</script>


<style lang="scss" scoped>
  .progressbar {
    position: relative;
    margin-top: 30px;
    
    &__bg {
      width: 66vw;
      height: 2vh;
      background: #1C7817;
      border-radius: 32px;  
      z-index: -2;
    }

    &__progress {
      position: absolute;
      height: 2vh;
      border-radius: 32px;  
      background: linear-gradient(180deg, #FFF32A 0%, rgba(240, 160, 162, 0.5) 180%);
    }
  }
</style>