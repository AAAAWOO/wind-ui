<template>
  <button class="wind-button" :class="classes" :disabled="disabled">
    <span v-if="loading" class="wind-loadingIndicator"></span>
    <slot />
  </button>
</template>

<script lang="ts">
import { computed } from "vue";

export default {
  props: {
    theme: {
      type: String,
      default: "button"
    },
    size: {
      type: String,
      default: "normal"
    },
    level: {
      type: String,
      default: "normal"
    },
    disabled: {
      type: Boolean,
      default: false
    },
    loading: {
      type: Boolean,
      default: false
    }
  },
  setup(props) {
    const { theme, size, level } = props
    const classes = computed(() => {
      return {
        [`wind-theme-${theme}`]: theme,
        [`wind-size-${size}`]: size,
        [`wind-level-${level}`]: level,
      }
    })
    return { 
      classes 
    }
  }
}
</script>

<style lang="scss">
$blue: #2269E7;
$red: #ff585d;
$grey: #7c7e8c;
$white: #ffffff;
.wind-button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  white-space: nowrap;
  height: 34px;
  padding: 0 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  color: #44475b;
  background: $white;
  box-shadow: 0 1px 0 fade-out(#000, 0.95);
  cursor: pointer;
  transition: background-color 250ms;
  & + & {
    margin-left: 8px;
  }
  &:hover,
  &:focus {
    color: $blue;
    border-color: $blue;
  }
  &:focus {
    outline: none;
  }
  &::-moz-focus-inner {
    border: 0;
  }
  &.wind-theme-link {
    border-color: transparent;
    box-shadow: none;
    color: $blue;
    &:hover,
    &:focus {
      color: lighten($blue, 10%);
    }
  }
  &.wind-theme-text {
    border-color: transparent;
    box-shadow: none;
    color: inherit;
    &:hover,
    &:focus {
      background: darken($white, 5%);
    }
  }
  &.wind-size-big {
    font-size: 24px;
    height: 48px;
    padding: 0 16px;
  }
  &.wind-size-small {
    font-size: 12px;
    height: 20px;
    padding: 0 4px;
  }
    &.wind-theme-button {
    &.wind-level-main {
      background: $blue;
      color: $white;
      border-color: $blue;
      &:hover,
      &:focus {
        background: darken($blue, 10%);
        border-color: darken($blue, 10%);
      }
    }
    &.wind-level-danger {
      background: $red;
      border-color: $red;
      color: $white;
      &:hover,
      &:focus {
        background: darken($red, 10%);
        border-color: darken($red, 10%);
      }
    }
  }
  &.wind-theme-link {
    &.wind-level-danger {
      color: $red;
      &:hover,
      &:focus {
        color: darken($red, 10%);
      }
    }
  }
  &.wind-theme-text {
    &.wind-level-main {
      color: $blue;
      &:hover,
      &:focus {
        color: darken($blue, 10%);
      }
    }
    &.wind-level-danger {
      color: $red;
      &:hover,
      &:focus {
        color: darken($red, 10%);
      }
    }
  }
  &.wind-theme-button {
    &[disabled] {
      cursor: not-allowed;
      color: $grey;
      &:hover {
        border-color: $grey;
      }
    }
  }
  &.wind-theme-link, &.wind-theme-text {
    &[disabled] {
      cursor: not-allowed;
      color: $grey;
    }
  }
  > .wind-loadingIndicator{
    display: inline-block;
    width: 10px;
    height: 10px;
    margin-right: 4px;
    border-color: $blue $blue $blue transparent;
    border-style: solid;
    border-width: 2px;
    border-radius: 8px;
    animation: wind-spin 1s infinite linear;
  }
}
@keyframes wind-spin {
  0%{transform: rotate(0deg)} 
  100%{transform: rotate(360deg)} 
}
</style> 