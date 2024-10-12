<template>
  <div class="max-w-[1400px] m-auto">
    <a-page-header
        class="teacher-page-header"
        :breadcrumb="breadCrumbConfig"
    >
      <template #title>
        <div class="flex items-center">
          <h1 class="text-2xl font-bold"> Danh sách giáo viên tại HOCPTE</h1>
        </div>
      </template>
      <template #extra>
        <a-input
            placeholder="Tìm kiếm giáo viên"
            class="w-[300px]"
            size="large"
        />
      </template>

      <div class="page_infor float-right text-[12px] flex items-center">
        <span class="mr-[5px]">1/50</span>
        <span class="flex items-center p-[5px] bordered border-[1px] bg-white hover:bg-[#F5F5F5] cursor-pointer">
            <left-outlined/>
          </span>
        <span class="flex items-center p-[5px] bordered border-[1px] bg-white hover:bg-[#F5F5F5] cursor-pointer">
            <right-outlined/>
          </span>
      </div>

      <div class="grid xl:grid-cols-5 sm:grid-cols-3 grid-cols-2 mt-[35px] md:gap-[10px] lg:gap-x-0 mb-[50px]">
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
        <TeacherCard class="scale-[0.9] md:scale-[1]"/>
      </div>
    </a-page-header>

  </div>
</template>

<script setup>
import {
  LeftOutlined,
  RightOutlined,
} from "@ant-design/icons-vue";
import {h} from "vue";

const breadCrumbConfig = {
  routes: [
    {
      path: "/",
      breadcrumbName: "Trang chủ",
    },
    {
      path: "#",
      breadcrumbName: "Danh sách giáo viên",
    },
  ],
  itemRender: (routes) => {

    console.log('route', routes)
    return h('a',
        {
          href: routes.route.path,
          class: routes.route.path === '#' ? 'text-[#40a9ff] cursor-default' : 'text-[#40a9ff] hover:text-[#1890ff]'
        },
        routes.route.breadcrumbName
    );
  },
};
</script>

<style>

@media (max-width: 768px) {
  .teacher-page-header {
    padding: 5px !important;
  }
}
</style>

