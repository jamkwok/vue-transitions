<template>
  <div class="hello">
    <button @click="show = !show">
      Toggle
    </button>
    <transition name="fade">
      <p v-if="show" style="font-size:300%;">hello</p>
    </transition>
    <div id="f1_container">
      <div id="f1_card" class="shadow">
        <div class="front face">
          <img src="https://previews.123rf.com/images/alhovik/alhovik1307/alhovik130700018/20751296-Scallop-seashell-Stock-Vector-shell.jpg" width="304" height="304"/>
        </div>
        <div class="back face center">
          <p>This is nice for exposing more information about an image.</p>
          <p>Any content can go here.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      show: true,
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0
}
#f1_container {
  position: relative;
  margin: 0px auto;
  width: 304px;
  height: 304px;
  z-index: 1;
}
#f1_container {
  perspective: 1000;
}
#f1_card {
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: all 1.0s linear;
}
#f1_container:hover #f1_card {
  transform: rotateY(180deg);
  box-shadow: -5px 5px 5px #aaa;
}
.face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}
.face.back {
  display: block;
  transform: rotateY(180deg);
  box-sizing: border-box;
  padding: 10px;
  color: white;
  text-align: center;
  background-color: #aaa;
}
</style>
