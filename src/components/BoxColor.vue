<template>
  <div :style="{background:hex}"> 
    <!-- doit passer un objet au style. si propriété avec un tiret: il faut que la propriété soit en string -->
    <!-- <div :style="{'background-color':hex}"> -->
    <p>Color box: {{hex}}</p>
  </div>
</template>

<script>

function valid(v) {
  return v>=0 && v<=255
}

export default {
  props: {
    r: {
      type:Number,
      validator: v => valid(v)
    },
    g: {
      type:Number,
      validator: v => valid(v)
    },
    b: {
      type:Number,
      validator: v => valid(v)
    }
  },
  methods: {
    rgbToHex(c) {
      var hex = c.toString(16);
      return hex.length == 1 ? "0" + hex : hex;
    },
    setHex() {
      this.hex = "#" + this.rgbToHex(this.r) + this.rgbToHex(this.g) + this.rgbToHex(this.b);
    }
  },
  data(){
    return{
      hex: null,
    }
  },
  created() {
    this.setHex()
  }
}
</script>

<style>

.color-box {
  width: 500px;
  background-color:rgb(r, g, b)
}
</style>