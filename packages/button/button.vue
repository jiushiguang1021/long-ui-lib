<template>
  <div class="wt-button" :class="className()">
    <i :class="icon" v-if="icon"></i>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      // 组件显示的文字
      type: String,
      default: () => {
        return "button";
      },
    },
    icon: {
      // 组件显示的图标（可选）
      type: String,
      default: () => {
        return "";
      },
    },
    type: {
      // 组件类型，（可选）主要是背景色的不同（可选值："primary", "danger")
      type: String,
      default: () => {
        return "default";
      },
    },
    size: {
      // 组件的大小  （可选）（可选值："normal", "small",  "large")
      type: String,
      default: () => {
        return "normal";
      },
    },
  },
  methods: {
    // 拼接class
    className() {
      return this.type + " " + this.size;
    },
  },
};
</script>

<style lang="scss" scoped>
.wt-button {
  background: #fff;
  color: #333;
  border: 1px solid #eee;
  text-align: center;
  border-radius: 0.2rem;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  i {
    margin: 0 0.2rem;
  }
  &:active {
    background: #eee;
  }
  &.primary {
    background: #1bb5f1;
    color: #fff;
    border: 0;
    &:active {
      background: #62c3e9;
    }
  }
  &.danger {
    background: #ef4f4f;
    color: #fff;
    border: 0;
    &:active {
      background: #ff6969;
    }
  }
  &.normal {
    height: 2rem;
    line-height: 2rem;
    font-size: 0.8rem;
    width: 50%;
  }
  &.small {
    height: 1.5rem;
    line-height: 1.5rem;
    font-size: 0.7rem;
    width: 30%;
  }
  &.large {
    height: 2.5rem;
    line-height: 2.5rem;
    font-size: 0.9rem;
    width: 100%;
  }
}
</style>