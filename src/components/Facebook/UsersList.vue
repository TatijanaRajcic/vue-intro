<template>
  <div>
    <p v-for="(user, i) in users" :key="i">{{user.firstName}}</p>
  </div>
</template>

<script>

export default {
  props: {
    users: Array
  }
}
</script>

<style>

</style>