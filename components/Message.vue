<template>
  <dl class="message message--self">
    <dt class="message__icon">
      <img src="~@/assets/img/self.png" alt="" />
    </dt>
    <dd class="message__text message__text--self">{{ msg }}</dd>
  </dl>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data: function () {
    return {}
  },
  props: {
    msg: {
      type: String,
      default: '',
    },
  },
})
</script>
