<template>
  <div class="small">
    <img
      :src="item"
      v-for="(item, index) in image"
      :key="index"
      class="image"
      @click="sendImage(item, index)"
    />
  </div>
</template>

<script>
export default {
  name: "SmallImage",
  props: {
    image: {
      type: Array,
      default: () => [],
    },
  },

  created() {
    console.log("created", this.image);
  },
  methods: {
    sendImage(url, index) {
      this.$emit("selectedImg", {url, index});
    },
  },
};
</script>
<style scoped>
.image {
  width: 150px;
  height: 150px;
  padding-top: 5px;
  padding-right: 5px;
  padding-left: 5px;
  padding-bottom: 5px;
  cursor: pointer;
}
.small {
  margin-top: 10px;
  display: flex;
  justify-content: left;
  align-items: left;
}
.image:hover {
  border: 2px solid rgb(0, 0, 0);
}
</style>
