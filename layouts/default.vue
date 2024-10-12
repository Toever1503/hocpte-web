<template>
  <a-layout >
    <headers/>
    <div class="main_page_content relative z-0 min-h-[700px] bg-white  w-full m-auto">
      <slot/>
    </div>

    <footers/>
    <a-tooltip>
      <template #title>Về đầu trang</template>
      <a-back-top />
    </a-tooltip>

  </a-layout>
</template>

<style>
a {
  color: black;
}
</style>