<template>
  <div>
    <LocaleSwitcher />
    <div class="heading">
      <div class="title">
        <h1>PUG<span class="epk">epk</span></h1>
        <div class="overlay"></div>
      </div>
    </div>
    <div class="container my-5">
      <Bio />
    </div>
    <div class="album">
      <div class="text-center container">
      </div>
    </div>
    <div class="videos">
      <div class="text-center container">
        <iframe width="100%" height="500" src="https://www.youtube.com/embed/qOpgV2a2y6M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
    <div class="stage-plot">
      <div class="text-center container">
        <h2 class="mb-5 text-uppercase">{{$t('stage-plot')}}</h2>
        <img class="mw-100 mb-5" src="/assets/images/plot.png" alt="">
      </div>
    </div>
    <channel-list />
  </div>
</template>

<script>
import channelList from '@/components/channelList';
import Bio from '@/components/bio';
import LocaleSwitcher from './localeSwitcher.vue';
//import stagePlot from '@/components/stagePlot';
export default {
  name: 'Epk',
  components: {
    channelList, Bio, LocaleSwitcher
  },
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');
  .heading {
    background: url('/assets/images/bg-main.jpeg');
    background-attachment: fixed;
    height: 100vh;
    background-size: cover;
    background-position: center;
    position: relative;
    .title {
      position: absolute;
      height: 100vh;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      z-index: 2;
      h1 {
        font-size: 64px;
        margin-top: -50px;
        position: relative;
        .epk {
          font-family: 'New Tegomin';
          font-size: 22px;
          position: absolute;
          right: -8px;
          top: -8px;
          transform: rotate(-10deg);
          color: #fff;
          z-index: 2;
          padding: 1px 3px 9px 3px;
          //background: rgba(0,0,0,.8);
          text-shadow: 0 0 10px #000;
          border-radius: 2px;
          line-height: 20px;
        }
      }
      .overlay {
        z-index: -1;
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background-image: linear-gradient(0deg,rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.25) 25%, rgba(0, 0, 0, 0.50) 50%, rgba(0, 0, 0, 0.25) 75%, rgba(0, 0, 0, 0) 100%);
      }
    }
  }
  .stage-plot {
    padding: 50px 0;
    background: rgba(0,0,0,.5);
  }
  @media (max-width: 992px) {
    .heading {
      max-height: 300px;
      background-repeat: no-repeat;
      background-attachment: unset;
      .title {
        max-height: 300px;
      }
    }
  }
</style>
