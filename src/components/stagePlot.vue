<template>
  <div class="container">
    <div class="instrument-list">
      <div class="row">
        <div class="col-md-6" v-for="i in instruments" :key="i">
          <div class="inst"><div :class="i">{{i}}</div></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StagePlot',
  data() {
    return {
      instruments: [
        'amp',
        'ride',
        'crash',
        'floortom',
        'tom',
        'hihat'
      ]
    }
  }
}
</script>

<style scoped lang="scss">
  .instrument-list {
    max-width: 400px;
  }
  .inst {
    width: 150px;
    height: 150px;
    display: flex;
    align-items: center;
    justify-content: center;
    > div {
      background: #fff;
      border: 2px solid #000;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #000;
      font-size: 14px;
      font-weight: 600;
      text-transform: uppercase;
    }
    .amp {
      width: 150px;
      height: 80px;
      border-radius: 8px;
    }
    .ride {
      width: 120px;
      height: 120px;
      border-radius: 120px;
    }
    .crash {
      width: 100px;
      height: 100px;
      border-radius: 100px;
    }
    .floortom {
      width: 90px;
      height: 90px;
      border-radius: 90px;
    }
    .tom {
      width: 80px;
      height: 80px;
      border-radius: 80px;
    }
    .hihat {
      width: 70px;
      height: 70px;
      border-radius: 70px;
    }
  }
</style>
