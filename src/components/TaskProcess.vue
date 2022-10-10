<template>
  <div class="progress-bar">
      <span>{{progress}}%</span>
      <div class="progress" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
    props:{
        progress:{
            type: Number,
            default: 0
        }
    }
}
</script>

<style>
    .progress-bar{
        width: 70vw;
        height: 30px;
        border: 1px solid #fff;
        border-radius: 10px;

        position: relative;
        display: flex;
        align-items: center;
    }

    .progress-bar span{
        font-size: 16px;
        position: absolute;
        left: calc(50% - 16px);
        z-index: 1000;
    }

    .progress{
        height: 30px;
        background-color: green;
        border-radius: 10px;
    }

   
</style>