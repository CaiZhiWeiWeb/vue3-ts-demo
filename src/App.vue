<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  <OptionsApi :message="obj" />
  <ZuheApi message="Welcome to Your Vue.js + TypeScript App"/>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import OptionsApi from "./components/OptionsApi.vue";
import ZuheApi from "./components/ZuheApi.vue"

interface Obj {
  title: string;
  okMessage: string;
  cancelMessage: string;
}

const App = defineComponent({
  data() {
    return {
      obj: {
        title: "czw",
        okMessage: "确定",
        cancelMessage: "取消",
      } as Obj,
    };
  },
  components: {
    HelloWorld,
    OptionsApi,
    ZuheApi
  },
});

export default App;
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
