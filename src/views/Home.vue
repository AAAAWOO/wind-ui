<template>
  <Topnav />
  <div class="home">
    <div class="content">
      <div class="main">
        <h1 class="name">
          <span class="object">Wind UI</span>
        </h1>
        <p class="text">简洁有效的组件库</p>
        <p class="tagline">少即是多，多则更多</p>
        <div class="actions">
          <div class="action">
            <router-link class="homeButton page" to="/doc">快速开始</router-link>
          </div>
          <div class="action">
            <a class="homeButton code" href="https://github.com/AAAAWOO/wind-ui">查看源码</a>
          </div>
        </div>
      </div>
      <div class="image">
        <div class="image-container">
          <svg>
            <use xlink:href="#icon-wind1"></use>   
          </svg>
        </div>
      </div>
    </div>

    <div class="features">
      <div class="items">
        <div class="item">
          <article class="feature">
            <div class="icon">⚡️</div>
            <h2 class="title">技术新颖</h2>
            <p class="detail">基于 Vue 3</p>
          </article>
        </div>
        <div class="item">
          <article class="feature">
            <div class="icon">🔩</div>
            <h2 class="title">安全保证</h2>
            <p class="detail">采用 TypeScript</p>
          </article>
        </div>
        <div class="item">
          <article class="feature">
            <div class="icon">🔑</div>
            <h2 class="title">效率无忧</h2>
            <p class="detail">门槛低上手快</p>
          </article>
        </div>
        <div class="item">
          <article class="feature">
            <div class="icon">📦</div>
            <h2 class="title">资源丰富</h2>
            <p class="detail">组件持续更新</p>
          </article>
        </div>
        <div class="item">
          <article class="feature">
            <div class="icon">💡</div>
            <h2 class="title">代码易读</h2>
            <p class="detail">重构简洁明晰</p>
          </article>
        </div>
        <div class="item">
          <article class="feature">
            <div class="icon">🛠️</div>
            <h2 class="title">使用便捷</h2>
            <p class="detail">文档反复斟酌</p>
          </article>
        </div>
      </div>
    </div>
    <br />
  </div>
</template>

<script lang="ts">
import Topnav from "../components/Topnav.vue";

export default {
  components: {
    Topnav
  }
}
</script>

<style lang="scss" scoped>
$blue: #2269E7;
$blue2: #1c55b8;
.home {
  width: 100%;
  max-width: 100%;
  margin: 0 auto;
  flex-grow: 1;
  flex-shrink: 0;
  
  > .content {
    display: flex;
    flex-direction: column;
    max-width: 1152px;
    text-align: center;
    padding: 60px 24px 48px;
    margin: 0 auto;

    > .main {
      position: relative;
      z-index: 10;
      order: 2;
      flex-grow: 1;
      flex-shrink: 0;

      > .name {
        color: transparent;

        > .object {
          background: -webkit-linear-gradient(120deg, $blue2 30%, $blue);
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
        }
      }

      > .name,
      .text {
        margin: 0 auto;
        padding-bottom: 8px;
        letter-spacing: -0.4px;
        line-height: 40px;
        font-size: 32px;
        font-weight: bold;
        white-space: pre-wrap;
        color: #33261c;
      }

      > .tagline {
        margin: 0 auto;
        max-width: 329px;
        line-height: 28px;
        font-size: 18px;
        font-weight: medium;
        white-space: pre-wrap;
        color: rgba(60 60 60 / 70%);
      }

      > .actions {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        margin: -6px;
        padding-top: 24px;

        > .action {
          flex-shrink: 0;
          padding: 6px;

          > .homeButton {
            display: inline-block;
            border: 1px solid transparent;
            border-radius: 20px;
            padding: 0 20px;
            line-height: 38px;
            font-size: 14px;
            font-weight: 500;
            text-align: center;
            text-decoration: inherit;
            white-space: nowrap;
            touch-action: manipulation;
            transition-property: color, background-color, border-color;
            transition-duration: 0.25s, 0.25s, 0.25s;
            transition-timing-function: ease, ease, ease;
            transition-delay: 0s, 0s, 0s;
          }

          > .page {
            color: #ffffff;
            background-color: $blue;
            border-color: $blue;
          }

          > .page:hover {
            background-color: $blue2;
            border-color: $blue2;
          }

          > .code {
            border-color: #f2f2f2;
            background-color: #f2f2f2;
            color: #44475b;
          }

          > .code:hover {
            background-color: #d1d1d1;
            border-color: #d1d1d1;
          }
        }
      }
    }

    > .image {
      order: 1;

      > .image-container {
        position: relative;
        margin: 0 auto;
        width: 200px;
        height: 200px;

        > svg {
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
          width: 50%;
        }
      }
    }
  }

  > .features {
    position: relative;
    padding: 0 24px;
    margin: 0 auto;
    max-width: 1152px;

    > .items {
      display: flex;
      flex-wrap: wrap;
      margin: -8px;

      > .item {
        padding: 8px;
        width: 100%;

        > .feature {
          border: 1px solid #f9f9f9;
          border-radius: 12px;
          padding: 24px;
          height: 100%;
          background-color: #f9f9f9;

          > .icon {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;
            border-radius: 6px;
            background-color: #e5e5e5;
            width: 48px;
            height: 48px;
            font-size: 24px;
          }

          > .title {
            line-height: 24px;
            font-size: 16px;
            font-weight: 600;
          }

          > .detail {
            padding-top: 8px;
            line-height: 24px;
            font-size: 14px;
            font-weight: 500;
            color: rgba(60, 60, 60, 0.7);
          }
        }
      }
    }
  }
}

@media (min-width: 640px) {
  .home {
    .content {
      padding: calc(60px + 48px) 48px 64px;

      > .main {
        > .name,
        .text {
          max-width: 576px;
          line-height: 56px;
          font-size: 48px;
        }

        > .tagline {
          padding-top: 12px;
          max-width: 576px;
          line-height: 32px;
          font-size: 20px;
        }

        > .actions {
          padding-top: 32px;
        }
      }

      > .image {
        > .image-container {
          width: 400px;
          height: 400px;
        }
      }
    }

    .features {
      padding: 0 48px;

      > .items {
        > .item {
          width: 50%;
        }
      }
    }
  }
}

@media (min-width: 768px) {
  .home {
    > .features {
      .items {
        > .item {
          width: calc(100% / 3);
        }
      }
    }
  }
}

@media (min-width: 960px) {
  .home {
    padding-top: 60px;

    > .content {
      padding: 60px 64px 64px;
      text-align: left;
      display: flex;
      flex-direction: row;

      > .main {
        order: 1;
        width: calc((100% / 3) * 2);
        max-width: 592px;
        margin-left: 8px;

        > .name,
        .text {
          margin: 0;
          line-height: 64px;
          font-size: 56px;
        }

        > .tagline {
          margin: 0;
          line-height: 36px;
          font-size: 24px;
        }

        > .actions {
          justify-content: flex-start;
        }
      }

      > .image {
        flex-grow: 1;
        order: 2;
        margin: 0;
        min-height: 100%;

        > .image-container {
          display: flex;
          justify-content: center;
          align-items: center;
          width: 100%;
          height: 100%;
        }
      }
    }

    > .features {
      padding: 0 64px;
    }
  }
}

@media (min-width: 1024px) {
  .content {
    max-width: 1024px;
  }
}      
</style>