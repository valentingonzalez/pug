<template>
  <div class="locale-switcher">
    <div class="switch">
      <div class="lang-wrapper d-flex">
        <div class="lang selected">{{selectedLanguage}}</div>
        <div v-for="lang in langs.filter(e => e != selectedLanguage)" class="lang" :key="lang.code" @click="selectLanguage(lang)">
          {{ lang }}
        </div>
      </div>
    </div>
    <!--
    <select v-model="$i18n.locale">
      <option v-for="(lang, i) in langs" :key="`Lang${i}`" :value="lang">{{ lang }}</option>
    </select>-->
  </div>
</template>

<script>

export default {
  data() {
    return {
      langs: ['es', 'en'],
      selectedLanguage: null
    }
  },
  mounted() {
    this.selectLanguage(this.langs[0]);
  },
  methods: {
    selectLanguage(lang) {
      this.selectedLanguage = lang;
      this.$i18n.locale = lang;
    }
  }
}
</script>

<style scoped lang="scss">
  .locale-switcher {
    position: fixed;
    right: 20px;
    top: 20px;
    z-index: 1000;
    color: #151515;
    .switch {
      height: 26px;
      border-radius: 26px;
      background: #fff;
      position: relative;
      padding: 0 18px;
      font-size: 13px;
      font-weight: 800;
      text-transform: uppercase;
      display: flex;
      align-items: center;
      box-shadow: 0 0 3px rgba(0,0,0,.4);
      .lang-wrapper {
        overflow: hidden;
        max-width: 20px;
        transition: all .3s;
      }
      &:hover .lang-wrapper {
        max-width: 60px;
      }
      .lang {
        cursor: pointer;
        padding: 0 12px;
        border-right: 1px solid #ccc;
        &.selected,
        &:hover {
          color: #f18008;
        }
        &:first-child { padding-left: 0; }
        &:last-child { padding-right: 0;border-right: none; }
      }
      &::before {
        content: '';
        position: absolute;
        left: -4px;
        bottom: 0px;
        width: 11px;
        height: 10px;
        z-index: 20;
        background: url('data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyB3aWR0aD0iMTFweCIgaGVpZ2h0PSIxMHB4IiB2aWV3Qm94PSIwIDAgMTEgMTAiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8dGl0bGU+VHJpYW5nbGU8L3RpdGxlPgogICAgPGcgaWQ9IlBhZ2UtMSIgc3Ryb2tlPSJub25lIiBzdHJva2Utd2lkdGg9IjEiIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPGcgaWQ9IkFydGJvYXJkIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTUxLjAwMDAwMCwgLTEwOS4wMDAwMDApIiBmaWxsPSIjRkZGRkZGIj4KICAgICAgICAgICAgPHJlY3QgaWQ9IlJlY3RhbmdsZSIgeD0iMTU1IiB5PSI5MiIgd2lkdGg9IjE2NCIgaGVpZ2h0PSIyNiIgcng9IjEzIj48L3JlY3Q+CiAgICAgICAgICAgIDxwYXRoIGQ9Ik0xNTguMDYyMjU2LDEwOS4wMzcxMDkgTDE2MS45MjMwOTYsMTE1Ljk2MTQyNiBDMTYxLjQ0MzExNSwxMTYuNjY4Mjk0IDE2MC4xNTYxNjksMTE3LjM0NzgxOSAxNTguMDYyMjU2LDExOCBDMTU1Ljk2ODM0MywxMTguNjUyMTgxIDE1My43NzIwOTUsMTE4Ljk4ODM1IDE1MS40NzM1MTEsMTE5LjAwODUwNyBDMTU0LjI5MDAzOSwxMTcuNjg0ODI2IDE1Ni4wMzE2MzcsMTE2LjAyMjkyNiAxNTYuNjk4MzAzLDExNC4wMjI4MDggQzE1Ny4zNjQ5NywxMTIuMDIyNjkgMTU3LjgxOTYyMSwxMTAuMzYwNzkgMTU4LjA2MjI1NiwxMDkuMDM3MTA5IFoiIGlkPSJUcmlhbmdsZSI+PC9wYXRoPgogICAgICAgIDwvZz4KICAgIDwvZz4KPC9zdmc+');
      }
    }
  }
</style>