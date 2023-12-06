<template>
  <el-container >
    <el-main>
      <MainUI :isVisible="isVisible" :IPinfo="IPinfo"/>
      <br>
      <IPinfoUI :isVisible="isVisible" :IPinfo="IPinfo"/>
    </el-main>

  </el-container>
</template>

<script lang="ts" setup>
// import { useDark, useToggle } from '@vueuse/core'

// const isDark = useDark()
// const toggleDark = useToggle(isDark)
// toggleDark()
import MainUI from "./components/Main.vue"
import IPinfoUI from "./components/IPinfo.vue"
import header_icon from "./assets/logo.svg"
import { ref , reactive} from 'vue'
import { ElMessage } from 'element-plus'
import { toClipboard } from '@soerenmartius/vue3-clipboard'

const isVisible=ref(true)
const IPinfo=reactive({globalInfo:null,localInfo:null})

document.addEventListener("visibilitychange", function() {
  var string = document.visibilityState
  if (string === 'hidden')isVisible.value = false
  else isVisible.value = true
})
</script>

<style>

</style>
