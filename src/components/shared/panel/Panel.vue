<template>

<div class="panel">
  <h2 class="title-panel" @dblclick="visible = !visible">{{title}}</h2>
    <transition name="panel-fade">
      <div class="panel-content" v-show="visible">
        <slot></slot>
      </div>
    </transition>
</div>

</template>

<script>
export default {
  props: ['title'],
    data() {
      return {
        visible: true
      }
    }
}
</script>

<style scoped>
  .panel {
    padding: 0 auto;
    border: solid 2px grey;
    display: inline-block;
    margin: 5px;
    box-shadow: 5px 5px 10px grey;
    width: 200px;
    height: 100%;
    vertical-align: top;
    text-align: center;
  }
  .panel .title-panel {
    text-align: center;
    border: solid 2px;
    background: lightblue;
    margin: 0 0 15px 0;
    padding: 10px;
    text-transform: uppercase;
  }
  * {
    box-shadow: 5px 5px 5px;
  }

  .panel-fade-enter, .panel-fade-leave-active {
    opacity: 0
  }
  .panel-fade-enter-active, .panel-fade-leave-active {
    transition: opacity .4s
  }
</style>
