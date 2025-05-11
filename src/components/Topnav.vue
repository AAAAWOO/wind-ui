<template>
  <div class="topnav">
    <div class="topnav-container">
      <svg v-if="toggleMenuButtonVisible" class="toggleMenu" @click="toggleMenu">
        <use xlink:href="#icon-menu1"></use>
      </svg>
    
      <router-link to="/" class="logo">
        <svg class="icon">
          <use xlink:href="#icon-wind1"></use>
        </svg>
        <span class="canHide">Wind UI</span>
      </router-link>

      <nav class="navLinks canHide">
        <div class="navItem">
          <router-link to="/doc/intro">指南</router-link>
        </div>
        <div class="navItem">
          <router-link to="/doc/switch">组件</router-link>
        </div>
        <div class="navItem">
          |&nbsp;&nbsp;&nbsp;&nbsp;
          <a href="https://github.com/AAAAWOO/wind-ui">
            <svg class="icon">
              <use xlink:href="#icon-github"></use>
            </svg>
            GitHub
          </a>
        </div>
      </nav>
    </div>
  </div>
</template>

<script lang="ts">
import { inject, Ref } from "vue";

export default {
  props: {
    toggleMenuButtonVisible: {
      type: Boolean,
      default: false
    }
  },

  setup() {
    const menuVisible = inject < Ref < boolean >> ("menuVisible")           // get
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value
    }
    return {
      toggleMenu
    }
  }
}
</script>

<style lang="scss" scoped>
$blue: #2269E7;
.topnav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 60px;
  z-index: 20;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: saturate(50%) blur(8px);
  border-bottom: 1px solid #d9d9d9;
  > .topnav-container { 
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 24px;
    height: 100%;
    > .logo {
      display: inline-block;
      font-weight: 500;
      text-decoration: none;
      margin-right: auto;
      > svg {
        height: 2.2rem;
        width: 2.2rem;
        margin-right: 0.8rem;
        vertical-align: middle;
      }
      > span {
        font-size: 1.3rem;
        font-weight: bold;
        padding: 0 4px;
        color: #44475b;
        position: relative;
        vertical-align: middle;
      }    
    }
    > .navLinks {
      display: flex;
      white-space: nowrap;
      > .navItem {
        position: relative;
        display: inline-block;
        margin: 0 1rem;
        line-height: 2rem;
        > a {
          line-height: 1.4rem;
          color: inherit;
          font-weight: bold;
          text-decoration: none;
        }
        > a:hover {
          color: $blue;
        }
        > .router-link-active {
          color: $blue;
          font-weight: bolder;
          margin-bottom: -2px;
          border-bottom: 2px solid $blue;
        }
      }
    }
    > .toggleMenu {
      width: 24px;
      height: 24px;
      position: absolute;
      left: 16px;
      top: 50%;
      transform: translateY(-50%);  
      display: none;
    }
    @media (max-width: 500px) {
      .canHide {
        display: none;
      }
      > .navLinks {
        display: none;
      }
      > .logo {
        margin: 0 auto;
      }
      > .toggleMenu {
        display: inline-block;
      }
    }
  }
}  
</style>