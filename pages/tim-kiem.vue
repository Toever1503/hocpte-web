<template>
  <div id="search_page" class="w-[1400px] m-auto bg-white rounded">
    <a-page-header
        style="padding: 10px 5px"
        :breadcrumb="breadCrumbConfig"
    >
      <template #title>
        <div class="flex items-center">
          <div class="flex items-center">
            <h1 class="text-2xl font-bold"> 1 kết quả với từ khóa tìm kiếm:
              <span class="text-red-500">ssada</span>
            </h1>
          </div>
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

      <div>

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
      breadcrumbName: "Tìm kiếm",
    },
    {
      path: "#",
      breadcrumbName: "afffs",
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