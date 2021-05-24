<template>
  <dl class="message message__matsuko">
    <dt class="message__icon">
      <img src="@/assets/img/matsuko.png" alt="" />
    </dt>
    <dd v-if=(/しゅふ|主婦|カリスマ/.test(msg)) class="message__text">
      {{ msg }}？<br />カリスマ主婦ってさ、主婦じゃないじゃん。自転車の前と後ろに子供乗っけて大根持ってガーっみたいな、そういう人がカリスマ主婦よ
    </dd>
    <dd v-else-if=(/すき|好き|かわいい/.test(msg)) class="message__text">
      {{ msg }}？<br />とりあえず脱げる？話はそれからよ
    </dd>
    <dd v-else-if=(/元気|げんき|どう/.test(msg)) class="message__text">
      {{ msg }}？<br />落ち着きなさいよ。添い寝してあげよっか？
    </dd>
    <dd v-else-if=(/年齢|年|歳|いくつ|なんさい/.test(msg)) class="message__text">
      {{ msg }}？<br />忘れたわ
    </dd>
    <dd v-else-if=(/てんき|天気/.test(msg)) class="message__text">
      {{ msg }}？<br />自分で調べろ！くっだらねぇ！
    </dd>
    <dd v-else-if=(/体重|重い|たいじゅう/.test(msg)) class="message__text">
      {{ msg }}？<br />アタシ朝青龍よりデカイからね。
    </dd>
    <dd v-else-if=(/友達|ともだち|しんゆう/.test(msg)) class="message__text">
      {{ msg }}？<br />本当に友達なのかしら?金の切れ目が縁の切れ目よ。
    </dd>
    <dd v-else-if=(/デブ|太い|ふと/.test(msg)) class="message__text">
      {{ msg }}？<br />デブもここまでくれば、自慢せずにはいられないの。相撲取りでもプロレスラーでもなければ、大食い選手権やフードファイトクラブからのお誘いの声もかからない、ただのデブよ
    </dd>
    <dd v-else-if=(/死にたい|つらい|悲しい|かなしい|なく|泣く/.test(msg)) class="message__text">
      {{ msg }}？<br />傷つくから次にいけるのよ
    </dd>
    <dd v-else-if=(/わからない|どう/.test(msg)) class="message__text">
      {{ msg }}？<br />まだペットに逃げちゃダメよ！
    </dd>
    <dd v-else class="message__text">
      {{ msg }}？<br />
      {{ returnText[Math.floor(Math.random() * returnText.length)] }}
    </dd>
  </dl>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data: function () {
    return {
      returnText:[
        "アタシ朝青龍よりデカイからね。",
        "アナ夕、人生、舐め腐ってるわ。幸せの意味について、考えたことある?",
        "おのずと道は開かれるのよ。",
        "だからもう死んじゃったらいいんじゃないですか。",
        "ちょっと辛いことがあったとしても、すぐ坊主にしちゃダメよ。",
        "まだまだ日本は捨てたもんじゃないわよ。",
        "くっだらねぇ！バッカじゃねぇの！",
        "嫌いは好きの裏返し。本当の嫌いはさようなら。",
        "私思ったの。常に新しいことをし続けてないと人間ってダメになっちゃうなって。",
        "七夕なんか全部作り話だしね",
        "人生ってそんなに面白いことない。",
        "生きる事は、辛いことの連続です。",
        "知らない方がイイ事だらけよ、人生なんて",
        "鈍感であることって大事じゃない？幸せにおいて。",
      ]
    }
  },
  props: {
    msg: {
      type: String,
      default: '',
    },
  },
})
</script>
