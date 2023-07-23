<template>
  <div class="details">
    <Editor
      class="editos"
      :value="value"
      :locale="zhHans"
      @change="handleChange"
    />
  </div>
</template>
  
<script setup>
import "bytemd/dist/index.css"; // 导入编辑器样式
import { Editor } from "@bytemd/vue-next"; // 导入编辑器组件
import zhHans from "bytemd/lib/locales/zh_Hans.json"; // 汉化
import "highlight.js/styles/vs.css";
import "juejin-markdown-themes/dist/juejin.min.css"; // 其实就是需要这个css文件

import { ref } from "vue";
const value = ref("");
// 获取书写文档内容
const handleChange = (v) => {
  value.value = v;
};
// 上传图片 点击触发上传图片事件，大家获取文件把图片上传服务器然后返回url既可
// const uploadImage = async (files) => {
//   console.log("files", files);
//   return [
//     {
//       title: files.map((i) => i.name),
//       url: "http",
//     },
//   ];
// };
</script>

<style lang="scss">
.details {
  position: fixed;
  top: 30px;
  left: 0;
  width: 100vw;
  height: 100vh;
  .editos {
    .bytemd {
      height: calc(
        100vh - 200px
      ) !important; // 改变编辑器默认高度，不需要的可以不配置
    }
  }
}
</style>
  