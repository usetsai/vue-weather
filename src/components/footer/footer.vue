<template>
  <div class="footer">
    <span class="github icon-github"><a href="http://github.com/helianthuswhite/vue-weather"></a></span>
    <span class="change-city icon-501"><router-link to="/city"></router-link></span>
  </div>
</template>

<script>

  export default {
    props: ['weather'],
    data() {
      return {
      };
    }
  };
</script>

<style lang="less">
  .footer {
    position: fixed;
    display: flex;
    align-items: center;
    width: 100%;
    height: 45px;
    left: 0;
    bottom: 0;
    background: rgb(26, 55, 95);
    &::before {
      position: absolute;
      width: 100%;
      left: 0;
      top: 0;
      border: solid 1px rgba(255, 255, 255, 0.3); 
      content: '';
      display: block;
      box-sizing: border-box;
    }
    @media (min-device-pixel-ratio: 1.5),(-webkit-min-device-pixel-ratio: 1.5) {
      &::before {
        transform: scaleY(0.7);
        -webkit-transform: scaleY(0.7);
      } 
    }
    @media (min-device-pixel-ratio: 2),(-webkit-min-device-pixel-ratio: 2) {
      &::before {
        transform: scaleY(0.5);
        -webkit-transform: scaleY(0.5);
      } 
    }
    span {
      display: inline-block;
      box-sizing: border-box;
      width: 35px;
      height: 35px;
      color: #fff;
      font-size: 35px;
      &.github {
        margin-left: 15px;
      }
      &.change-city {
        position: absolute;
        right: 15px;
      }
      a {
        display: block;
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
      }
    }
  }
</style>
