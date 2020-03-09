<template>
  <p>Random value between {{min}} and {{max}}: {{getRandom()}}</p>
</template>

<script>
export default {
  props: {
    min: Number,
    max: Number
  },
  methods: {
    getRandom() {
      return Math.floor(Math.random() * (this.max - this.min) + this.min)
    }
  }
}
</script>

<style>

</style>