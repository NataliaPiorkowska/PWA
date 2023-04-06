<template>
    <div>
        <img :src="image" class="img" @click="showModal"/>
    </div>
</template>
<script>

export default {
  name: 'BigImage',
  props:{
    image:{
        type:String,
        default: ()=>'pusty string'
    }
  },

  methods: {
    showModal() {
      this.$emit('rm', true)
    }
  }

}
</script>
<style scoped>
.img{
    width:48.5%;
    height: 600px;
    cursor: pointer;
}
</style>