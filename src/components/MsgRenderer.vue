<template>
  <div class="wrapper">
    <div v-for="(msg, i) in msgs" :key="i" :class="[{ self: msg.self, system: msg.type === 'system' }]">
      <template v-if="msg.type !== 'system'">
        <img class="avator" :src="msg.user.avator" />
        <div class="content">
          <p class="nickname" v-if="!msg.self">{{ msg.user.nickname }}</p>
          <component :is="comMap[msg.type]" v-bind="msg.content" :self="msg.self" />
        </div>
      </template>
      <component v-else :is="comMap[msg.type]" v-bind="msg.content" />
    </div>
  </div>
</template>

<script>
import ImgMsg from './msg-types/img.vue'
import SystemMsg from './msg-types/system.vue'
import TextMsg from './msg-types/text.vue'

export default {
  name: 'MsgRenderer',
  props: {
    msgs: Array,
    default() {
      return []
    }
  },
  data() {
    return {
      comMap: {
        img: ImgMsg,
        system: SystemMsg,
        text: TextMsg
      }
    }
  }
}
</script>
<style scoped lang="scss">
.avator {
  width: 30px;
  height: 30px;
  padding: 4px;
  border: 1px solid #b0b3b3;
  border-radius: 3px;
}
.content {
  margin: 0 10px;
}
.nickname {
  color: #b0b3b3;
  font-size: 13px;
  margin-bottom: 5px;
}
.wrapper {
  & > div {
    display: flex;
    margin: 20px;
    &.system {
      justify-content: center;
    }
    &.self {
      flex-direction: row-reverse;
      .content {
        text-align: right;
      }
    }
  }
}
</style>
