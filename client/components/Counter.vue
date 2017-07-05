<template>

    <div class="counter-wrapper">
      <div class="counter">
        {{ count }}
      </div>
      <button @click="$store.commit('INCREMENT')">Increment</button>
      <button @click="$store.commit('DECREMENT')">Decrement</button>
      <button @click="$store.dispatch('incrementAsync')">Increment Async</button>
      <p>
        To get started, edit files in <code>./client</code> and save.
      </p>
    </div>

</template>


<script>
import ActionHeader from './ActionHeader.vue';

export default {
  components: {
    ActionHeader
  },
  props: {
    target: Object
  },
  computed: {
    count() {
      return this.$store.state.count;
    }
  }
}
</script>

<style lang="stylus" scoped>
.counter {
  margin: 100px auto;
  border-radius: 3px;
  width: 200px;
  height: 200px;
  text-align: center;
  line-height: 200px;
  font-size: 5rem;
  background-color: #f0f0f0;
  user-select: none;
}

.instance
  font-family Menlo, Consolas, monospace
  &.inactive
    opacity .5


.self
  cursor pointer
  position relative
  overflow hidden
  z-index 2
  background-color $background-color
  transition background-color .1s ease
  border-radius 3px
  font-size 14px
  line-height 22px
  height 22px
  white-space nowrap
  &:hidden
    display none
  &:hover
    background-color #E5F2FF
  &.selected
    background-color $active-color
    .arrow
      border-left-color #fff
    .instance-name
      color #fff
  .app.dark &
    background-color $dark-background-color
    &:hover
      background-color #444
    &.selected
      background-color $active-color

.children
  position relative
  z-index 1

.content
  position relative
  padding-left 22px

.info
  color #fff
  font-size 10px
  padding 3px 5px 2px
  display inline-block
  line-height 10px
  border-radius 3px
  position relative
  top -1px
  &.console
    color #fff
    background-color transparent
  &.router-view
    background-color #ff8344
  &.fragment
    background-color #b3cbf7
  &.inactive
    background-color #aaa
  &:not(.console)
    margin-left 6px

.arrow-wrapper
  position absolute
  display inline-block
  width 16px
  height 16px
  top 0
  left 4px

.arrow
  position absolute
  top 5px
  left 4px
  transition transform .1s ease, border-left-color .1s ease
  &.rotated
    transform rotate(90deg)

.angle-bracket
  color #ccc

.instance-name
  color $component-color
  margin 0 1px
  transition color .1s ease
</style>
