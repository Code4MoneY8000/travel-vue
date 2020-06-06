<template>
    <div class="list">
      <div class="item" v-for="(item,key) of cities" :key='key'>{{key}}</div>
    </div>
</template>

<script>
export default {
  name: 'cityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
.list
  display: flex
  flex-direction: column
  justify-content: center
  position: absolute
  top: 1.78rem
  right: 0
  bottom: 0
  width: .4rem
  .item
    text-align: center
    color: #00bcd4
    line-height: .4rem
</style>
