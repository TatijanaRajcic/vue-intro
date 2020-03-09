<template>
  <div class="home">
    <IdCard :userInfo="users[0]" @user-clicked="handleClick"/>
    <IdCard :userInfo="users[1]" @user-clicked="handleClick"/>
    <p v-if="clickedUser">
      user clicked: {{clickedUser}}
    </p>
    <Random :min="2" :max="6"/>
    <BoxColor :r="255" :g="0" :b="0"/>
    <Rating :rate="3.2"/>
    <Facebook />
  </div>
</template>

<script>
// @ is an alias to /src
import IdCard from "@/components/IdCard.vue";
import Random from "@/components/Random.vue";
import BoxColor from "@/components/BoxColor.vue";
import Rating from "@/components/Rating.vue";
import Facebook from "@/components/Facebook/Facebook.vue";

export default {
  name: "Home",
  data() {
    return {
      clickedUser: null,
      users: [
        {
          lastName:'Doe',
          firstName:'John',
          gender:'male',
          height:178,
          birth:new Date("1992-07-14"),
          picture:"https://randomuser.me/api/portraits/men/44.jpg"
        },{
          lastName:'Delores ',
          firstName:'Obrien',
          gender:'female',
          height: 172,
          birth:new Date("1988-05-11"),
          picture:"https://randomuser.me/api/portraits/women/44.jpg"
        }]
    }
  },
  components: {
    IdCard,
    Random,
    BoxColor,
    Rating,
    Facebook
  },
  methods: {
    handleClick(user){
      this.clickedUser = user;
    }
  }
};
</script>
