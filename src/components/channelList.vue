<template>
  <div class="container">
    <h2 class="text-center mb-5">CHANNEL LIST</h2>
    <div class="row channels">
      <div class="col-md-6">
        <div class="channel" v-for="(c, i) in channelsFirstHalf" :key="`channel${i}`">
          <div class="num">{{c.num}}</div>
          <div class="inst">{{c.inst}}</div>
          <div class="conn">{{c.conn}}</div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="channel" v-for="(c, i) in channelsSecondHalf" :key="`channel${i}`">
          <div class="num">{{c.num}}</div>
          <div class="inst">{{c.inst}}</div>
          <div class="conn">{{c.conn}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChannelList',
  data() {
    return {
      channels: [
        { num: '1', inst: 'kick', conn: 'shure beta 52' },
        { num: '2', inst: 'snare', conn: 'shure SM57' },
        { num: '3', inst: 'hi-hat', conn: 'shure SM57' },
        { num: '4', inst: 'tom', conn: 'Senheiser E604' },
        { num: '5', inst: 'floor tom', conn: 'shure SM57' },
        { num: '6', inst: 'oh 1', conn: 'AKG C414' },
        { num: '7', inst: 'oh 2', conn: 'AKG C414' },
        { num: '8', inst: 'Octapad', conn: 'Line DI' },
        { num: '9', inst: 'Octapad', conn: 'Line DI' },
        { num: '10', inst: 'bass amp', conn: 'Line DI' },
        { num: '11', inst: 'guitar amp', conn: 'shure SM57' },
        { num: '12', inst: 'synth', conn: 'shure beta 52' },
        { num: '13', inst: 'keyboards', conn: 'Line DI' },
        { num: '14', inst: 'keyboards', conn: 'Line DI' },
        { num: '15', inst: 'Synth', conn: 'Line DI' },
        { num: '16', inst: 'vocals', conn: 'shure beta 58' },
        { num: '17-18', inst: 'vocals', conn: 'shure beta 58 (stereo XLR)' },
        { num: '19', inst: 'vocals', conn: 'shure beta 58' },
        { num: '20', inst: 'vocals', conn: 'shure beta 58' },
      ]
    }
  },
  computed: {
    channelsFirstHalf() {
      // or instead of floor you can use ceil depending on what side gets the extra data

      return  this.channels.slice(0, Math.ceil(this.channels.length / 2));
    },
    channelsSecondHalf() {
      return this.channels.slice(Math.ceil(this.channels.length / 2), this.channels.length);
    }
  }
}
</script>

<style scoped lang="scss">
.channels {
  margin-bottom: 100px;
  .channel {
    display: flex;
    align-items: center;
    text-transform: capitalize;
    padding: 5px;
    border-bottom: 1px dashed rgb(85, 85, 85);
    .num {
      min-width: 55px;
      font-weight: bold;
    }
    .inst {
      flex-grow: 1;
    }
  }
}
</style>
