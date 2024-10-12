<template>
  <div class="search_box grid items-center">
    <div class="hidden sm:grid">
      <a-input-search class="min-w-[215px] font-normal "
                      v-model:value="value"
                      @pressEnter="search"
                      @search="search"
                      placeholder="Nhập từ khóa bạn cần tìm"
      />
    </div>

    <span class="cursor-pointer sm:hidden text-[#00000073]">
      <search-outlined @click="openSubDiagSearch"/>
    </span>

    <div id="subDialogSearch"
         class="bg-[#00000030] hidden duration-500 ease-in-out fixed w-full h-full top-0 left-0 pt-[100px] z-1"
         @click="closeSubDialogSearch">
      <div class="bg-white max-w-[250px] m-auto rounded p-[10px] min-h-[120px] relative z-2">
        <h3 class="text-center m-0">Nhập từ khóa cần tìm kiếm</h3>
        <a-input class="font-normal" style="border: 1px solid gainsboro" v-model:value="value" placeholder="...."/>

        <close-outlined class="absolute right-0 top-0 m-2 hover:text-gray-400 duration-300 ease-in-out"
                        @click="closeSubDialogSearch($event, true)"/>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  SearchOutlined,
  CloseOutlined,
} from "@ant-design/icons-vue";
import {message} from "ant-design-vue";
import {ref} from "vue";

const value = ref(""); // value of input search

const search = () => {
  // only search when people type something
  console.log('search: ', value.value === '');
  if (!value.value)
    message.error('Vui lòng nhập từ khóa cần tìm kiếm');
  else
    window.location.replace(`/tim-kiem?q=${value.value}`);
}

const openSubDiagSearch = () => {
  document.querySelector('#subDialogSearch').classList.remove('hidden');
}
const closeSubDialogSearch = (e, isBtn = false) => {
  if (isBtn) {
    value.value = "";
    document.querySelector('#subDialogSearch').classList.add('hidden');
  } else if (e.target.id === 'subDialogSearch') {
    value.value = "";
    e.target.classList.add('hidden');
  }
}

</script>


<style>

header .search_box input, header .ant-input-group-addon > button {
  border: none;
}
</style>