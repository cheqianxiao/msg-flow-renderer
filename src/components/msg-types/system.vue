<template>
  <p>{{ msg }}</p>
</template>

<script>
export default {
  name: 'SystemMsg',
  props: {
    type: String,
    invitor: String,
    member: String,
    time: Number
  },
  computed: {
    msg() {
      const { type } = this
      if (type === 'time') {
        const date = new Date(this.time)
        console.log(date.getFullYear())
        const year = date.getFullYear()
        const month = date.getMonth() + 1
        const day = date.getDate()
        const hour = date.getHours()
        const minutes = date.getMinutes()
        return `${year}年${month}月${day}日  ${hour}:${minutes}`
      } else if (type === 'invite') {
        const { invitor, member } = this
        return `「${invitor}」 邀请 「${member}」 加入群组`
      }
    }
  }
}
</script>
<style scoped>
p {
  color: #b3b2b2;
  font-size: 13px;
}
</style>
