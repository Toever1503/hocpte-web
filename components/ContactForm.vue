<template>
  <div id="contact_form">
    <div class="form_contact py -[50px]">
      <a-form
          :model="formState"
          name="basic"
          :wrapper-col="{ span: 16 }"
          autocomplete="off"
      >
        <a-form-item
            name="username"
            :rules="[{ required: true, message: 'Vui lòng điền họ tên!' }]"
        >
          <a-input v-model:value="formState.username" placeholder="Họ và Tên"/>
        </a-form-item>

        <a-form-item
            name="password"
            :rules="[{ required: true, message: 'Vui lòng điền số điện thoại!' }]"
        >
          <a-input v-model:value="formState.password" placeholder="Số điện thoại"/>
        </a-form-item>

        <a-form-item
            name="username"
            :rules="[{ required: true, message: 'Vui lòng điền địa chỉ email!' }]"
        >
          <a-input v-model:value="formState.username" placeholder="Địa chỉ email"/>
        </a-form-item>

        <a-form-item
            name="password"
            :rules="[{ required: true, message: 'Vui lòng không để trống!' }]"
        >
          <a-input v-model:value="formState.password" placeholder="Bạn muốn tư vấn thông tin như thế nào?"/>
        </a-form-item>

        <a-form-item class="text-center">
          <a-button class="hover:scale-[1.1] ease-in-out duration-300" type="primary" html-type="submit">Gửi thông tin</a-button>
        </a-form-item>
      </a-form>
    </div>
  </div>
</template>

<script setup>

import {reactive} from "vue";

const formState = reactive({
  username: '',
  password: '',
  remember: true,
});
</script>

<style>
.form_contact .ant-col.ant-col-16.ant-form-item-control {
  margin: auto;
}
</style>