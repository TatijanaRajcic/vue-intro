<template>
  <div class="facebook">
    <Filters 
      v-once
      :countries="filterCountries()" 
      @filter-used="filterIronhackers"
    />
    <UsersList :users="users" />
  </div>
</template>

<script>
import Filters from "./Filters"
import UsersList from "./UsersList"
import json from "@/data/berlin.json"

export default {
  components: {
    Filters,
    UsersList
  },
  data() {
    return {
      users: json,
    }
  },
  methods: {
    filterCountries() {
      return [...new Set(this.users.map(d => d.country))]
    },
    filterIronhackers(country) {
      this.users = 
        country === "All" 
        ? json
        : json.filter(user=>user.country === country)
    }
  }
}
</script>

<style>

</style>