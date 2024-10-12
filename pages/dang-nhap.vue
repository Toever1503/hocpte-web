<template>
  <div class="max-w-[500px] m-auto mt-[20px] ease-in-out duration-300 sm:m-auto sm:mt-[100px] bg-white shadow-md rounded bordered border-[1px] p-[20px]">

    <h1 class="text-center text-2xl mb-10">Đăng nhập</h1>

    <a-form
        :model="formState"
        name="basic"
        @finish="onFinish"
        @finishFailed="onFinishFailed"
    >
      <a-form-item
          label="Tài khoản"
          name="userName"
          :rules="[{ required: true, message: 'Tài khoản không được để trống!' }]"
      >
        <a-input v-model:value="formState.userName" placeholder="Tài khoản hoặc email"/>
      </a-form-item>

      <a-form-item
          label="Mật khẩu"
          name="password"
          :rules="[{ required: true, message: 'Mật khẩu không được để trống!' }]"
      >
        <a-input-password v-model:value="formState.password" placeholder="..."/>
      </a-form-item>

      <div class="text-[12px] sm:pl-[82px]">
        <a-checkbox v-model:checked="formState.remember">Nhớ</a-checkbox>
        <NuxtLink to="/dang-ky" class="float-right">Chưa có tài khoản?</NuxtLink>
      </div>

      <div class="grid gap-[10px]">
        <a-button class="m-auto block" size="small" type="primary" html-type="submit">Đăng nhập</a-button>

        <a-divider style="line-height: 0">
          <span class="text-[12px]">Hoặc đăng nhập bằng</span>
        </a-divider>

        <a-space>
          <a-button style="display: flex" class="flex gap-[5px] items-center" size="small">
            <google-outlined style="color:red"/>
            <span class="text-[11px]">Google</span>
          </a-button>

          <a-button style="display: flex" class="gap-[5px] items-center" size="small">
            <facebook-outlined style="color: #04A7E6"/>
            <span class="text-[11px]">Facebook</span>
          </a-button>
        </a-space>

      </div>
    </a-form>
  </div>
</template>
<script setup>
import {
  GoogleOutlined,
  FacebookOutlined
} from "@ant-design/icons-vue";
import {reactive} from 'vue';


const formState = reactive({
  userName: '',
  password: '',
  remember: true,
})

const onFinish = (values) => {
  console.log('Success:', values);
};

const onFinishFailed = (errorInfo) => {
  console.log('Failed:', errorInfo);
};
</script>

<style>
.main_page_content{
  background: white;
}
</style>