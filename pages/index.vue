<template>
  <div class="slide-container" id="slide-container">
    <div class="slide-page page1">
      <div class="container">
        <h2>page1</h2>
        <p>page1 content</p>
        <div class="step step1 animated fadeIn" data-delay="1000"></div>
        <div class="step step2 animated fadeIn"></div>
      </div>
    </div>
    <div class="slide-page page2">
      <div class="container">
        <h2>page2</h2>
        <p>page2 content</p>
        <h2>Page2 - 延迟播放动画</h2>
        <div class="step step1 animated rollIn" data-delay="1000"></div>
        <div class="step step2 animated rollIn" data-delay="1500"></div>
        <div class="step step3 animated rollIn" data-delay="2000"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head: {
      link: [
        {
          rel: "styleSheet",
          href: 'https://cdn.jsdelivr.net/gh/lipten/slidePage/dist/slidePage.min.css'
        }
      ],
      script: [
        { src: 'https://cdn.jsdelivr.net/gh/lipten/slidePage/dist/slidePage.min.js' }
      ]
  },
  mounted() {
    // if (process.client) {
    //   const slidepage = new slidePage();
    //   console.log(666)
    // }
    if (process.browser) {
        console.log(666)
      var slidepage = new slidePage({
        slideContainer: '#slide-container',
        slidePages: '.slide-page',
        page: 1,
        refresh: true,
        dragMode: false,
        useWheel: true,
        useSwipe: true,
        useAnimation : true,

        // Events
        before: function(origin,direction,target){},
        after: function(origin,direction,target){},
      });
    }
  }
}
</script>

<style>

  .page1 {
    background-color: #3b8070;
  }
  .page2 {
    background-color: #9a20a7;
  }
  .page1 .step1 {
    position: absolute;
    top: 100px;
    left: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(178, 116, 57);
    border-radius: 50%;
  }

  .page1 .step2 {
    position: absolute;
    bottom: 100px;
    right: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(116, 178, 9);
  }

  .page2 .step1 {
    position: absolute;
    top: 100px;
    right: 5%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(82, 110, 178);
    border-radius: 50%;
  }

  .page2 .step3 {
    position: absolute;
    bottom: 60px;
    left: 19%;
    text-align: center;
    width: 150px;
    height: 150px;
    background-color: rgb(178, 79, 54);
  }

  .page2 .step2 {
    position: absolute;
    top: 100px;
    left: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(116, 178, 9);
  }

  .page3 .step1 {
    position: absolute;
    top: 100px;
    left: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(178, 79, 65);
    border-radius: 50%;
  }

  .page3 .step2 {
    position: absolute;
    bottom: 100px;
    right: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(52, 178, 89);
  }

  .page4 .container {
    padding-bottom: 20px;
  }

  .page4 ul {
    margin: 0;
    padding: 0;
    width: 90%;
    margin-left: 5%;
  }

  .page4 ul li {
    width: 100%;
    padding: 100px 10px;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    border-bottom: 1px solid rgb(83, 83, 83);
    background: rgba(255, 255, 255, .5);
    text-align: center;
  }

  .page5 .step2 {
    position: absolute;
    top: 100px;
    left: 19%;
    text-align: center;
    width: 150px;
    height: 100px;
    background-color: rgb(178, 159, 44);
  }

  .page5 .step1 {
    position: absolute;
    bottom: 100px;
    left: 19%;
    text-align: center;
    width: 100px;
    height: 100px;
    background-color: rgb(178, 72, 91);
  }

  .page5 .step3 {
    position: absolute;
    bottom: 100px;
    left: 60%;
    text-align: center;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background-color: rgb(93, 163, 178);
  }
</style>
