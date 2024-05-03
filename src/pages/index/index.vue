<script setup lang="ts">
import { getHomeBannerAPI, getHomeCategoryAPI } from '@/services/home'
import type { BannerItem } from '@/types/home'
import { onLoad } from '@dcloudio/uni-app'
import CustomNavbar from './components/CustomNavbar.vue'
import { ref } from 'vue'
import CategoryPanel from './components/CategoryPanel.vue'

// 获取轮播图数据
const bannerList = ref<BannerItem[]>([])

const getHomeBannerData = async () => {
  const res = await getHomeBannerAPI()
  bannerList.value = res.result
}

const getHomeCategoryaData = async () => {
  const res = await getHomeCategoryAPI()
  console.log(res)
}

//页面加载
onLoad(() => {
  getHomeBannerData()
  getHomeCategoryaData()
})
</script>

<template>
  <CustomNavbar />
  <XtxSwiper :list="bannerList" />
  <!-- 分类面板 -->
  <CategoryPanel />
</template>

<style lang="scss">
page {
  background-color: #f7f7f7;
}
</style>
