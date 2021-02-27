<template>
  <p :class="{ self }">{{ text }}</p>
</template>

<script>
export default {
  name: 'TextMsg',
  props: {
    text: String,
    self: Boolean
  }
}
</script>
<style lang="scss" scoped>
$wechat-green: #b0e46e;
p {
  padding: 7px 10px;
  background-color: #fff;
  position: relative;
  border-radius: 4px;
  &:after {
    content: '';
    display: block;
    position: absolute;
    border-width: 5px 6px 5px 10px;
    border-color: transparent #fff transparent transparent;
    border-style: solid;
    top: 10px;
    right: 100%;
  }
  &.self {
    background-color: $wechat-green;
    &:after {
      border-width: 5px 10px 5px 6px;
      border-color: transparent transparent transparent $wechat-green;
      left: 100%;
    }
  }
}
</style>
