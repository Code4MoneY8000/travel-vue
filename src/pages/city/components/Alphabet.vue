<template>
    <div class="list">
      <div class="item" v-for="item of letters" :key='item'
      :ref='item'
      @click='handleClick'
      @touchstart.prevent='handleTouchstart'
      @touchmove='handleTouchmove'
      @touchend='handleTouchend'>
      {{item}}
      </div>
    </div>
</template>

<script>
export default {
  name: 'cityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      timer: null,
      startY: 0
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchstart () {
      this.touchStatus = true
    },
    handleTouchmove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 88.4
          const move = Math.floor((touchY - this.startY) / 20)
          if (move >= 0 && move < this.letters.length) {
            this.$emit('change', this.letters[move])
          }
        }, 8)
      }
    },
    handleTouchend () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.list
  display: flex
  flex-direction: column
  justify-content: center
  position: absolute
  top: 0
  right: 0
  bottom: 0
  width: .4rem
  .item
    text-align: center
    color: #00bcd4
    line-height: .4rem
</style>
