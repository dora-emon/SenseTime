<template>
  <div class="hello">
    <button @click="changeLangEvent">切换语言</button>
    <span>{{$t('m.music')}}</span>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      locale: 'zh-CN', // 语言标识
      // this.$i18n.locale // 通过切换locale的值来实现语言切换
      messages: {
        'zh-CN': require('@/lang/zh-CN/index'), // 中文语言包
        'en-US': require('@/lang/en-US/index') // 英文语言包
      }
    }
  },
  methods: {
    changeLangEvent () {
      if (this.lang === 'zh-CN') {
        this.lang = 'en-US'
        this.$i18n.locale = this.lang// 关键语句
      } else {
        this.lang = 'zh-CN'
        this.$i18n.locale = this.lang// 关键语句
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
