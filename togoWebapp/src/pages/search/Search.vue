<template>
  <div>
    <router-link to="/">{{$store.state.city}}</router-link>
    <testvuex @changeVal="changeCity"></testvuex>
  </div>
</template>

<script>
import testvuex from './components/test_vuex'
export default {
  name: 'Search',
  data () {
    return {
      city: "城市"
    }
  },
  components: {
    testvuex
  },
  methods: {
    changeCity (res) {
      this.city = res || '城市'
    }
  }
}
</script>

<style lang='less' scoped>

</style>
