<template>
  <div class="list">
    <div class="item"
    v-for="(item,index) of list"
    :key="index"
    >
      <div class="item-title">
        {{item.title}}
        <div v-if="item.children">
          <detail-list :list='item.children'></detail-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    padding: 0 .2rem
    line-height: .8rem
</style>
