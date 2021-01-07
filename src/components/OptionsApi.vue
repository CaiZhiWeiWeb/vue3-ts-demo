<template>
  <div class="demo">
    <h2>option api</h2>
    {{this.message.okMessage}}--{{this.message.title}}
  </div>
</template>

// options api
<script lang="ts">
// eslint-disable-next-line no-unused-vars
import { defineComponent, PropType } from "vue";

interface ComplexMessage {
  title: string;
  okMessage: string;
  cancelMessage: string;
}

const Component = defineComponent({
  props: {
    name: String,
    success: { type: String },
    callback: {
      type: Function as PropType<() => void>,
    },
    message: {
      type: Object as PropType<ComplexMessage>,
      required: true,
      validator(message: ComplexMessage) {
        return !!message.title;
      },
    },
  },
});
export default Component;
</script>