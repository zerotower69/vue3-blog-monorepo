<!--
 * @Author: zerotower69 zerotower@163.com
 * @Date: 2022-12-16 21:48:34
 * @LastEditors: zerotower69 zerotower@163.com
 * @LastEditTime: 2022-12-16 21:56:14
 * @FilePath: /vue3-blog/packages/components/App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
<el-config-provider 
:button="config"
:locale="locale"
>
<router-view 
v-slot="{Component,route}">
 <keep-alive>
        <component
          :is="Component"
          v-if="route.meta.keepAlive"
          :key="route.name"
        />
      </keep-alive>
      <component
        :is="Component"
        v-if="!route.meta.keepAlive"
        :key="route.name"
      />
</router-view>
</el-config-provider>
</template>
<script lang="ts" setup name="App">
import zhCn from "element-plus/lib/locale/lang/zh-cn"
import { reactive, ref } from "vue"

const config = reactive({
    autoInsertSpace:false
})
const locale=ref(zhCn)
</script>