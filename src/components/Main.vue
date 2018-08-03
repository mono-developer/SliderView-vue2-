<template>
  <div id="app">
    <div class="border1">
      <p>Actual ad dimensions: 300 x 524</p>
      <VueDragResize ref="el1" :isActive="true" :w="size1.width" :h="size1.height" :minw="524" :minh="300" :isDraggable="false" :sticks="['ml','mr']"
        :style="{width: `${size1.width}px`, height: `${size1.height}px`}" @resizing="resize1">
        <iframe src="http://adpiler.s3.eu-central-1.amazonaws.com/ads/52516abf46eda87ed4f7123e11c50578_html/WM-banner-test-300-970x250-m-afisha.html" width="100%" height="100%" frameborder="0"></iframe>
        <button v-on:click="adChange1">Show Ad in 300 x 600</button>
      </VueDragResize>
    </div>

    <div class="border1" style="width: 50%">
      <p>Actual ad dimensions: 300 x 524</p>
      <VueDragResize :isActive="true" :w="size2.width" :h="size2.height" :minw="524" :minh="300" :isDraggable="false" :sticks="['bm']"
        :style="{width: `${size2.width}px`, height: `${size2.height}px`}" @resizing="resize2">
        <iframe src="http://adpiler.s3.eu-central-1.amazonaws.com/ads/52516abf46eda87ed4f7123e11c50578_html/WM-banner-test-300-970x250-m-afisha.html" width="100%" height="100%" frameborder="0"></iframe>
        <button v-on:click="adChange2">Show Ad in 300 x 600</button>
      </VueDragResize>
    </div>

    <div class="border1">
      <p>Actual ad dimensions: 300 x 524</p>
      <VueDragResize :isActive="true" :w="size3.width" :h="size3.height" :minw="524" :minh="300" :isDraggable="false" :aspectRatio="true" :sticks="['br']"
        :style="{width: `${size3.width}px`, height: `${size3.height}px`, top: '0px', left: '0px'}" @resizing="resize3">
        <iframe src="http://adpiler.s3.eu-central-1.amazonaws.com/ads/52516abf46eda87ed4f7123e11c50578_html/WM-banner-test-300-970x250-m-afisha.html" width="100%" height="100%" frameborder="0"></iframe>
        <button v-on:click="adChange3">Show Ad in 300 x 600</button>
      </VueDragResize>
    </div>


  </div>
</template>

<script>
import VueDragResize from 'vue-drag-resize'
// let width1 = 524
// let height1 = 300
export default {
  name: 'HelloWorld',
  components: {
    VueDragResize
  },
  data: function () {
    return {
      size1: {
        width: 524,
        height: 300
      },
      size2: {
        width: 524,
        height: 300
      },
      size3: {
        width: 524,
        height: 300
      }
    }
  },
  methods: {
    resize1 (newRect) {
      this.size1.width = newRect.width
      this.size1.height = newRect.height
    },
    resize2 (newRect) {
      this.size2.width = newRect.width
      this.size2.height = newRect.height
    },
    resize3 (newRect) {
      this.size3.width = newRect.width
      this.size3.height = newRect.height
    },
    adChange1 () {
      this.size1.width = 600
      this.size1.height = 300
    },
    adChange2 () {
      this.size2.width = 600
      this.size2.height = 300
    },
    adChange3 () {
      this.size3.width = 600
      this.size3.height = 300
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .border1 {
    padding: 30px;
    border: 1px solid;
    width: 90%;
    min-width: 700px;
    display: block;
    margin: 0 auto;
    background-color: lightgray;
    margin-bottom: 150px;
  }
  p {
    border: 1px solid;
    width: 300px;
    height: 40px;
    line-height: 40px;
    display: block;
    margin: 0 auto;
    margin-top: -50px;
    /* left: 0; */
    background-color: white;
    z-index: 99;
    margin-bottom: 20px;
  }
  .vdr{
      position: relative;
      display: block;
      margin: 0 auto;
      border: 2px solid;
  }

  .vdr.active:before{
    outline: none;
  }
  .vdr .vdr-stick-mr {
    border: 2px solid red;
  }
  button {
    margin-top: 60px;
    height: 40px;
    font-size: 16px;
  }

  iframe {
    background-color: #fff;
  }

  .vdr .vdr-stick-mr {
    border: 3px solid green !important;
  }
</style>
