<template>
  <img :src="imgUrl" />
</template>

<script>
export default {
  name: 'ImgMsg',
  props: {
    imgUrl: String
  }
}
</script>
<style scoped>
img {
  max-width: 200px;
}
</style>
