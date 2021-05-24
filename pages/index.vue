<template>
  <div class="container">
    <header class="header">
      <h1 class="header__title">マツコチャットボット</h1>
      <p class="header__description">マツコに質問する（24時間対応）</p>
      <p class="header__icon">
        <img src="~@/assets/img/matsuko.png" alt="" />
      </p>
    </header>
    <div class="main" id="main">
      <dl class="message">
        <dt class="message__icon">
          <img src="@/assets/img/matsuko.png" alt="" />
        </dt>
        <dd class="message__text">えっ！質問！？なに！</dd>
      </dl>
      <div v-for="(data, index) in dataList" :key="index">
        <Message :msg="data.message" />
        <transition appear>
          <div v-if="show">
            <Matsuko :msg="data.message" />
          </div>
        </transition>
      </div>
    </div>
    <footer>
      <div class="submit">
        <input type="text" class="submit__text" v-model="message" />
        <button value="送信" class="submit__button" v-on:click="append">
          送信
        </button>
      </div>
      <div class="copy">matsuko chat bot</div>
    </footer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data: function () {
    return {
      message: '',
      dataList: [],
      show: true,
    }
  },
  methods: {
    append() {
      if (this.message) {
        this.dataList.push({
          message: this.message,
        })
        //0.8秒後にスクロール最下部に移動※.bind(this)必須
        setTimeout(
          function () {
            const main: any = document.getElementById('main')
            let scrollHeight = main.scrollHeight
            main.scrollTop = scrollHeight
          }.bind(this),
          600
        )
        this.message = ''
      }
    },
  },
})
</script>

<style scoped lang="scss">
.v-enter-active,
.v-leave-active {
  transition: opacity 0s 0.8s;
}

.v-enter,
.v-leave-to {
  opacity: 0;
}
</style>
