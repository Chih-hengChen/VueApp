<template>
  <ContentBase>
    <h3>This is a small Vue App project.</h3>
    <br/>
    <dl class="row">
      <dt class="col-sm-3">技术使用</dt>
      <dd class="col-sm-9">Bootstrap + Vue + Ajax</dd>

      <dt class="col-sm-3">完成日期</dt>
      <dd class="col-sm-9">
        <p>2022/06/07</p>
      </dd>

      <dt class="col-sm-3">作者</dt>
      <dd class="col-sm-9">
        <p>Eric Chen <a href="https://github.com/Chih-hengChen">Github</a></p>
      </dd>

      <dt class="col-sm-3">功能</dt>
      <dd class="col-sm-9">实现了登录类似微博的应用，可
        <router-link :to="{name : 'login'}">登录</router-link> 和
        <router-link :to="{name : 'register'}">注册</router-link>
        发帖删帖，可持久化到服务器上</dd> 
    </dl>
  </ContentBase>
</template>

<script>

import ContentBase from '@/components/ContentBase.vue';



export default {
  name: 'HomeView',
  components: {
    ContentBase,
  }
}
</script>

<style scoped>
h3 {
  text-align: center;
}

dl {
  margin-left: 10px;
}
</style>