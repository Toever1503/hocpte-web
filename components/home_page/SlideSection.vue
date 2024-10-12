<template>
  <section class="section_slides">
    <a-carousel arrows>
      <template #prevArrow>
        <div class="custom-slick-arrow" style="left: 10px; z-index: 1">
          <left-circle-outlined/>
        </div>
      </template>
      <template #nextArrow>
        <div class="custom-slick-arrow" style="right: 10px">
          <right-circle-outlined/>
        </div>
      </template>

      <div class="h-[400px] w-full">
        <img class="w-full h-full object-fill" src="https://static.vecteezy.com/system/resources/previews/002/294/192/large_2x/online-class-web-banner-design-free-vector.jpg" >
      </div>

      <div class="h-[400px] w-full">
        <img class="w-full h-full object-fill" src="https://static.vecteezy.com/system/resources/previews/002/294/192/large_2x/online-class-web-banner-design-free-vector.jpg" >
      </div>

      <div class="h-[400px] w-full">
        <img class="w-full h-full object-fill" src="https://static.vecteezy.com/system/resources/previews/002/294/192/large_2x/online-class-web-banner-design-free-vector.jpg" >
      </div>

      <div class="h-[400px] w-full">
        <img class="w-full h-full object-fill" src="https://static.vecteezy.com/system/resources/previews/002/294/192/large_2x/online-class-web-banner-design-free-vector.jpg" >
      </div>
    </a-carousel>
  </section>
</template>

<script setup>
import {LeftCircleOutlined, RightCircleOutlined} from '@ant-design/icons-vue';


</script>

<style scoped>
/* For demo */
.section_slides .ant-carousel :deep(.slick-slide) {
  text-align: center;
  height: 400px;
  line-height: 160px;
  background: #364d79;
  overflow: hidden;
}

.section_slides .ant-carousel :deep(.slick-arrow.custom-slick-arrow) {
  width: 25px;
  height: 25px;
  font-size: 25px;
  color: #fff;
  background-color: rgba(31, 45, 61, 0.11);
  opacity: 0.3;
  z-index: 1;
}

.section_slides .ant-carousel :deep(.custom-slick-arrow:before) {
  display: none;
}


</style>