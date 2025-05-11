<template>
  <h1>Button 按钮</h1>
  <Demo :component="Button1Demo" />
  <Demo :component="Button2Demo" />
  <Demo :component="Button3Demo" />
  <Demo :component="Button4Demo" />
  <Demo :component="Button5Demo" />
  <div class="link">
    <span>
      &lt;
      <router-link to="/doc/switch">Switch 开关</router-link>
    </span>
    <span>
      <router-link to="/doc/dialog">Dialog 对话框</router-link>
      &gt;
    </span>
  </div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import Button1Demo from "./Button1.demo.vue";
import Button2Demo from "./Button2.demo.vue";
import Button3Demo from "./Button3.demo.vue";
import Button4Demo from "./Button4.demo.vue";
import Button5Demo from "./Button5.demo.vue";

export default {
  components: { 
    Demo
  },
  setup() {
    return {
      Button1Demo, Button2Demo, Button3Demo, Button4Demo, Button5Demo
    }
  }
}
</script>

<style lang="scss" scoped>
.link {
  display: flex;
  justify-content: space-between;
  color: #2269E7;
}
</style>