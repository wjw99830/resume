<template>
  <div id="container">
    <div class="resume">
      <span @click="toggles.个人信息 = true" class="entry" style="top: 30%; left: 20%">个人信息</span>
      <span @click="toggles.学习经历 = true" class="entry" style="top: 40%; left: 30%">学习经历</span>
      <span @click="toggles.实践经验 = true" class="entry" style="top: 50%; left: 40%">实践经验</span>
      <span @click="toggles.自我评价 = true" class="entry" style="top: 60%; left: 50%">自我评价</span>
      <span @click="toggles.发展方向 = true" class="entry" style="top: 70%; left: 60%">发展方向</span>
      <!-- <div class="modal" v-show="Object.values(toggles).some(Boolean)"> -->
        <transition name="pop-in">
        <div v-show="toggles.个人信息" class="card">
          <div class="card-header flex between align-center">
            <span class="card-title">个人信息</span>
            <i @click="toggles.个人信息 = false" class="fa fa-close"></i>
          </div>
          <div class="card-body flex column around align-center" style="height: calc(80% - 60px)">
            <img src="" alt="" class="avatar">
            <span style="font-size: 2rem">王济维</span>
            <small style="color: #b0b3b2">男 21岁 2020届毕业生</small>
            <a target="_blank" href="https://www.github.com/wjw99830">https://www.github.com/wjw99830</a>
            <small>942404649@qq.com</small>
            <small>手机号：15825526698</small>
            <span>Web前端开发</span>
            <span>杭州市</span>
          </div>
        </div>
        </transition>
        <transition name="pop-in">
        <div v-show="toggles.学习经历" class="card">
          <div class="card-header flex between align-center">
            <span class="card-title">学习经历</span>
            <i @click="toggles.学习经历 = false" class="fa fa-close"></i>
          </div>
          <div class="card-body">
            <p>就读院校：浙江省工商大学信息与电子工程学院</p>
            <p>专业：通信工程</p>
            <p>学历：本科</p>
            <p>于2017年7月网易前端微专业入门web前端，自学一年的过程中接触vue、react、es2015+等基础知识，主要知识来源为网上的博客、技术文章、MDN、各种API文档以及源码（Vue），学习时不区分领域界限，但侧重于学习js语言机制，在校期间学习过C/C++、java基本语法、操作系统、单片机汇编以及web系统设计与开发，对web后端知识有一定理解，能基于nodejs原生net模块封装上层websocket库，2018年9月开始全面使用typescript，并对其类型系统有一定理解，曾编写工具将java bean转换为ts interface，熟悉es2015+，能使用rollup打包并发布npm包，对编写测试用例有一定了解但实践不多，对Rust有一定兴趣，希望通过其学习系统级编程，学习兴趣侧重于工具开发或框架开发。</p>
          </div>
        </div>
        </transition>
        <transition name="pop-in">
        <div v-show="toggles.实践经验" class="card">
          <div class="card-header flex between align-center">
            <span class="card-title">实践经验</span>
            <i @click="toggles.实践经验 = false" class="fa fa-close"></i>
          </div>
          <div class="card-body">
            <p>实习经历：杭州领克信息技术有限公司</p>
            <p>工作描述：编写mes中后台界面，维护基于各种开源项目的上层封装，使用echarts渲染图表</p>
            <p style="border-bottom: 1px solid #eee; padding-bottom: 20px">工作职责：基于element-ui封装内部组件，前端环境搭建，快速产出页面</p>
            <p>代码实践：基于Vue 3 Function API封装中文多关键词搜索的可复用逻辑、基于Vue的美化滚动条、为元素可拖拽赋能的v-drag指令、参照koa洋葱模型实现的websocket封装以及对应的客户端、debounce、sleep等等工具函数，能基于Proxy实现响应式渲染库，并为其编写jsx插件，熟悉Vue的响应式原理以及组件渲染机制，对jsx有较大兴趣，会基本的部署流程，对Web Component有一定了解，能用原生js实现一些语言特性的polyfill，能用nodejs编写命令行程序，熟悉基本的git操作。</p>
          </div>
        </div>
        </transition>
        <transition name="pop-in">
        <div v-show="toggles.自我评价" class="card">
          <div class="card-header flex between align-center">
            <span class="card-title">自我评价</span>
            <i @click="toggles.自我评价 = false" class="fa fa-close"></i>
          </div>
          <div class="card-body">

          </div>
        </div>
        </transition>
        <transition name="pop-in">
        <div v-show="toggles.发展方向" class="card">
          <div class="card-header flex between align-center">
            <span class="card-title">发展方向</span>
            <i @click="toggles.发展方向 = false" class="fa fa-close"></i>
          </div>
          <div class="card-body"></div>
        </div>
        </transition>
      <!-- </div> -->
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { value } from 'vue-function-api'

export default Vue.extend({
  setup () {
    const toggles = value({
      个人信息: false,
      学习经历: false,
      实践经验: false,
      自我评价: false,
      发展方向: false
    })
    return {
      toggles
    }
  }
})
</script>

<style lang="scss">
* {
  // margin: 0;
  padding: 0;
  box-sizing: border-box;
  outline: none;
}
#container {
  font-family: Consolas, 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  position: absolute;
  width: 100%;
  height: 100%;
  color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
}
.avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 3px solid #eee;
}
</style>
