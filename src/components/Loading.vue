<template>
  <div class="d-flex flex-column justify-content-center align-items-center load-container">
    <h3>LOADING...</h3>
    <div class="lds-facebook"><div></div><div></div><div></div></div>
  </div>
</template>

<script>
export default {
  name: 'Loading'
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.load-container{
  height: 100vh;
}

h3{
  color:lighten($primary-color, 50%);
}

.lds-facebook {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-facebook div {
  display: inline-block;
  position: absolute;
  left: 8px;
  width: 16px;
  background: lighten($primary-color, 50%);
  animation: lds-facebook 1.2s cubic-bezier(0, 0.5, 0.5, 1) infinite;
}
.lds-facebook div:nth-child(1) {
  left: 8px;
  animation-delay: -0.24s;
}
.lds-facebook div:nth-child(2) {
  left: 32px;
  animation-delay: -0.12s;
}
.lds-facebook div:nth-child(3) {
  left: 56px;
  animation-delay: 0;
}
@keyframes lds-facebook {
  0% {
    top: 8px;
    height: 64px;
  }
  50%, 100% {
    top: 24px;
    height: 32px;
  }
}

</style>