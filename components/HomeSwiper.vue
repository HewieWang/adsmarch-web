<template>
  <div class="bg-black text-white p-8 relative">
    <Swiper
      :modules="[SwiperNavigation]"
      :slides-per-view="1.2"
      :space-between="16"
      :navigation="{ prevEl: '#prev-btn', nextEl: '#next-btn' }"
      :breakpoints="{
        '640': { slidesPerView: 2.2 },
        '1024': { slidesPerView: 4.2 }
      }"
      class="w-full"
    >
      <SwiperSlide v-for="(item, index) in list" :key="index">
        <div class="h-96 rounded-xl border border-gray-800 p-6 flex flex-col justify-between bg-gradient-to-b from-gray-900 to-black hover:border-blue-500 transition">
          <div>
            <h3 class="text-xl font-bold mb-2">{{ item.title }}</h3>
            <p class="text-sm text-gray-400">{{ item.desc }}</p>
          </div>
          <div class="text-blue-500">↗</div>
        </div>
      </SwiperSlide>
    </Swiper>

    <div class="flex justify-center space-x-4 mt-6">
      <button id="prev-btn" class="w-10 h-10 bg-white text-black rounded flex items-center justify-center hover:bg-gray-200">
        &lt;
      </button>
      <button id="next-btn" class="w-10 h-10 bg-blue-600 text-white rounded flex items-center justify-center hover:bg-blue-700">
        &gt;
      </button>
    </div>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation as SwiperNavigation } from 'swiper/modules'

import 'swiper/css'
import 'swiper/css/navigation'

const list = [
  { title: 'APP出海', desc: '助力 polybuzz 深耕 AI 社交全球投放' },
  { title: '跨境电商', desc: '推动 Yotobike 打造清晰购买路径' },
  { title: '广告设计', desc: '提供本地化创意设计与短视频制作' },
  { title: '海外KOL营销', desc: '陪伴 iFLYTEK 联盟营销与红人营' },
  { title: 'APP出海', desc: '助力 polybuzz 深耕 AI 社交全球投放' },
  { title: '跨境电商', desc: '推动 Yotobike 打造清晰购买路径' },
  { title: '广告设计', desc: '提供本地化创意设计与短视频制作' },
  { title: '海外KOL营销', desc: '陪伴 iFLYTEK 联盟营销与红人营' },
  
]
</script>