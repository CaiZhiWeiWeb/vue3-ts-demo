<template>
  <div class="zuhe">
    <h2>组合api</h2>
    <span v-for="(item,i) in result" :key="i">{{item}}</span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

const Component = defineComponent({
  props: {
    message: {
      type: String,
      required: true
    }
  },

  setup(props) {
    const result = props.message.split('') // 正确, 'message' 被声明为字符串
    const filtered = Object.keys(props) // 将引发错误: Property 'filter' does not exist on type 'string'
    console.log(result,filtered);
    return {
      result
    }
  }
})

export default Component
</script>

<style lang="css">
  .zuhe span{
    padding: 0 10px;
  }
</style>