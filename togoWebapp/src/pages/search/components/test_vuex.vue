<template>
  <div>
    <input type="text" v-model="inpVal">
    <div>
      <span @click="hh" v-for="(item,index) in lists" :key="index">{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'test_vuex',
  data () {
    return {
      inpVal: '',
      lists: ['郭','丽','荣']
    }
  },
  methods: {
    hh (e) {
      this.$emit('changeVal',e.target.innerText)
      this.$store.commit('changeCity',e.target.innerText)
    }
  },
  watch: {
    inpVal () {
      this.$emit('changeVal',this.inpVal)
    }
  }
}
</script>

<style lang='less' scoped>

</style>
