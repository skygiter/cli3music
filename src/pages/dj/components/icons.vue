<template>
  <div class="container border-bottom">
    <icon v-for="(item, index) in djIcons"
          :icons="item"
          :bgcolor="true"
          :key="index"
          @goPage="goPage(item.linkTo)"></icon>
  </div>
</template>

<script>
import { djIcons } from 'getInfos/getData'
import icon from 'base/icon'

export default {
  name: 'findIcon',
  data () {
    return {
      djIcons
    }
  },
  components: {
    icon
  },
  mounted () {
    this.iniData()
  },
  methods: {
    iniData () {
      this.djIcons = djIcons()
    },
    goPage (link) {
      this.$router.push(link)
    }
  }
}
</script>

<style lang="less" scoped>
@import url("~styles/global.less");

.container {
  .flex-around();
  width: 100%;
  height: 1.6rem;
  align-items: center;
  padding: 0.2rem 0 0.3rem;
}
</style>
