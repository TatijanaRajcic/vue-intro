<template>
  <div class="id-card" @click="$emit('user-clicked',userInfo)">
    <!-- dans le $emit, on met le nom de l'évènement, et l'info que l'on veut passer -->
    <img :src="userInfo.picture" class="avatar" alt="">
    <div class="info">
      <h2 class="fullname">{{userInfo.firstName}} {{userInfo.lastName}} - {{userInfo.gender === "male" ? "man" : "woman"}}</h2>
      <p>height: {{userInfo.height}}</p>
      <p>birthday: {{userInfo.birth}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    userInfo: Object
  }
}
</script>

<style lang="scss" scoped>
$color: dodgerblue;
.id-card {
  display: flex;
  text-align: left;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid;
  padding: 10px;
  margin-bottom: 20px;

  &:hover {
    background: $color;
  }
  .avatar {
    width: 120px;
    height: 120px;
    margin-right: 10px;
  }
  .title {
    margin-top: 0;
  }
  .fullname {
    font-weight: bold;
  }
}
</style>