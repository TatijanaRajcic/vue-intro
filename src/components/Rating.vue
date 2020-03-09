<template>
  <div class>
    <span v-for="n in 5" :key="n" v-html="getStar(n)"></span>
  </div>
</template>

<script>
export default {
  props: {
    rate: Number
  },
  methods:{
    getStar(v) {
      return v > this.rate ? "☆" : "★"
    }
  }
}
</script>

<style lang="scss">

</style>

