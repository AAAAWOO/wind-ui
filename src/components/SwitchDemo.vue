<template>
  <h1>Switch 开关</h1>
  <Demo :component="Switch1Demo" />
  <Demo :component="Switch2Demo" />
  <div class="link">
    <span>
      <router-link to="/doc/button">Button 按钮</router-link>
      &gt;
    </span>
  </div>
</template>

<script lang="ts">
import Demo from './Demo.vue';
import Switch1Demo from './Switch1.demo.vue';
import Switch2Demo from './Switch2.demo.vue';

export default {
  components: {
    Demo    
  },
  setup() {
    return {
      Switch1Demo, Switch2Demo
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