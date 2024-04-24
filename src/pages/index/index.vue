<script setup lang="ts">
import { getHomeBannerAPI } from '@/services/home'
import { onLoad } from '@dcloudio/uni-app'
import { CustomNavbar } from './components/CustomNavbar.vue'

const getHomeBannerData = async () => {
  const res = await getHomeBannerAPI()
  console.log(res)
}
onLoad(() => {
  getHomeBannerData()
})
</script>

<template>
  <CustomNavbar />
  <XtxSwiper />
</template>

<style lang="scss">
//
</style>
import type { getHomeBannerAPI } from '@/services/home'; import type { getHomeBannerAPI } from
'@/services/home'; import type { onLoad } from '@dcloudio/uni-app'; import type { onLoad } from
'@dcloudio/uni-app';
