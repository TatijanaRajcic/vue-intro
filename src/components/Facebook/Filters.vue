<template>
  <div>
    <button @click="$emit('filter-used','All')">All</button>
    <button v-for="(country,i) in countries" :key="i" @click="$emit('filter-used',country)">
      {{country}}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    countries: Array
  }
}
</script>

<style>

</style>