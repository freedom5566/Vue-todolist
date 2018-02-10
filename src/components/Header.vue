<!--HTML-->
<template>
    <div class="headerview">
        <h1>{{ msg }}</h1>
    </div>
</template>
<!--JS-->
<script>
  export default {
    data() {
      return {
        title: "魔鏡阿魔鏡，今天有甚麼事情"
      }
    },
    props: {
      msg: {
        type: String,
        default: "想覆蓋我嗎？去找父層吧"
      }
    }
  }
</script>
<!--CSS-->
<style>

</style>
