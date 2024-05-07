<template>
  <div class="text-block">
    <div>
      {{ $t('bio.p1') }}
      <br><br>
      <div class="flex-column flex-md-row d-flex align-items-center">
        <iframe class="w-100 mb-4 mb-md-0" src="https://open.spotify.com/embed/album/6l6Nw3eR6XmpFAVNbRFb4b" width="300" height="260" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
        <div class="ml-md-5">
          <div v-html="$t('bio.p2')"></div>
          <a class="link font-weight-bold small" @click.prevent="toggleCompleteBio" href="#">Read {{completeBio ? 'less' : 'more'}}</a>
        </div>
      </div>
      <div class="hidden-text mt-5" :class="{'visible' : completeBio}" v-html="$t('bio.p3')" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Bio',
  data() {
    return {
      completeBio: false
    }
  },
  methods: {
    toggleCompleteBio() {
      this.completeBio = !this.completeBio;
    }
  }
}
</script>

<style scoped lang="scss">
  .hidden-text {
    max-height: 0;
    transition: all .3s;
    overflow: hidden;
    &.visible {
      max-height: 800px;
    }
  }
</style>
