<template>
  <MsgRenderer :msgs="msgs" />
</template>

<script>
import MsgRenderer from './components/MsgRenderer.vue'
import img1 from './assets/img1.jpg'
import lily from './assets/lily.png'
import doudou from './assets/doudou.png'
import pp from './assets/pp.png'
export default {
  name: 'App',
  components: {
    MsgRenderer
  },
  data() {
    return {
      msgs: [
        {
          type: 'system',
          content: {
            type: 'invite',
            invitor: '豆豆',
            member: '小莉'
          }
        },
        {
          type: 'text',
          user: {
            avator: lily,
            nickname: '小莉'
          },
          self: false,
          content: {
            text: 'hola'
          }
        },
        {
          type: 'img',
          self: false,
          user: {
            avator: doudou,
            nickname: '豆豆'
          },
          content: {
            imgUrl: img1
          }
        },
        {
          type: 'system',
          content: {
            type: 'time',
            time: 1614409883598
          }
        },
        {
          type: 'text',
          self: true,
          user: {
            avator: pp,
            nickname: '泡泡'
          },
          content: {
            text: 'dejavu'
          }
        }
      ]
    }
  }
}
</script>
