<template>
  <div>
      <div class="color-list">
      <div
          class="color-item"
          v-for="(color,index) in colors" :style="'background-color:'+color.text" v-dragging="{ item: color, list: colors, group: 'color' }"
          :key="index"
      >{{color.text}}</div>
  </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      colors: [
        {
          text: "Aquamarine"
        },
        {
          text: "Hotpink"
        },
        {
          text: "Gold"
        },
        {
          text: "Crimson"
        },
        {
          text: "Blueviolet"
        },
        {
          text: "Lightblue"
        },
        {
          text: "Cornflowerblue"
        },
        {
          text: "Skyblue"
        },
        {
          text: "Burlywood"
        }
      ]
    };
  },
  methods: {
      
  },
  mounted() {
    this.$dragging.$on('dragged', ({ value }) => {
    //   console.log(value.item)
    //   console.log(value.list)
    //   console.log(value.otherData)
    })
    this.$dragging.$on('dragend', (res) => {
        //console.error(res);
    })
  }
};
</script>
<style scoped>
.color-item{
    width:100px;
    height:100px;
    display:inline-block;
    float:left;
    margin:5px;
}
</style>
