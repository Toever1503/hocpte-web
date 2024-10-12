<template>
  <a-drawer
      v-model:visible="props.visible"
      placement="right"
      @close="props.onClose"
  >
    <template #title>
    </template>

    <ul class="w-full sideBarNavLink text-[17px] divide-y">
      <li class="w-full relative">
        <div class="flex items-center p-[5px] justify-between">
          <a href="/" class="font-bold">
            Khóa học
          </a>
          <down-outlined @click="showCloseSubNavMenu"
                         class="text-[10px] cursor-pointer h-fit ease-in-out duration-300 hover:text-blue-400"/>
        </div>

        <div
            class="ease-in-out duration-1000 hidden bg-white leading-none w-[270px] py-[10px]"
            style="border-left: 1px solid #e5e7eb; ">
          <a href="#" class="p-[10px] pl-0 ml-2 font-bold cursor-auto hover:text-black block"
             style="border-bottom: 1px solid gainsboro">
            Khóa học online
          </a>
          <a class="hover:bg-[#F5F5F5] p-[10px] block" href="/">Luyện thi PTE 30</a>
          <a class="hover:bg-[#F5F5F5] p-[10px] block" href="/">Luyện thi PTE 30</a>
          <a class="hover:bg-[#F5F5F5] p-[10px] block" href="/">Luyện thi PTE 30</a>
          <a class="hover:bg-[#F5F5F5] p-[10px] block" href="/">Luyện thi PTE 30</a>
        </div>
      </li>

      <li class="w-full relative">
        <div class="flex items-center p-[5px] justify-between">
          <a href="/" class="font-bold">
            Tai lieu
          </a>
        </div>
      </li>

      <li class="w-full relative">
        <div class="flex items-center p-[5px] justify-between">
          <a href="/" class="font-bold">
            Tai lieu
          </a>
        </div>
      </li>

      <li class="w-full relative">
        <div class="flex items-center p-[5px] justify-between">
          <a href="/" class="font-bold">
            Tai lieu
          </a>
        </div>
      </li>

      <li class="w-full relative">
        <div class="flex items-center p-[5px] justify-between">
          <a href="/" class="font-bold">
            Tai lieu
          </a>
        </div>
      </li>
    </ul>
  </a-drawer>
</template>

<script setup>
import {
  DownOutlined,
} from "@ant-design/icons-vue";

const props = defineProps({
  visible: {
    type: Boolean,
    required: true,
  },
  onClose: {
    type: Function,
    required: true,
  },
});

const showCloseSubNavMenu = (e) => {
  console.log('e', e.target.parentElement.classList)

  if (e.target.parentElement.classList.contains('rotate-180')) {
    // close
  } else {
    // open
  }
  e.target.parentElement.classList.toggle('rotate-180');
};


</script>