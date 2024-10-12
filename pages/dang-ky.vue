<template>
  <div
      class="max-w-[500px] m-auto mt-[20px] ease-in-out duration-300 sm:m-auto sm:mt-[100px] bg-white shadow-md rounded bordered border-[1px] p-[20px]">

    <h1 class="text-center text-2xl mb-10">Đăng Ký Tài Khoản Mới</h1>

    <a-form
        ref="formRef"
        :model="formState"
        name="basic"
        @finish="onFinish"
        @finishFailed="onFinishFailed"
    >
      <a-form-item
          :label-col="{ span: 7 }"
          label="Họ và tên"
          name="fullName"
          :rules="[{ required: true, message: 'Tên không được để trống!' }]"
      >
        <a-input v-model:value="formState.fullName" placeholder="..."/>
      </a-form-item>
      <a-form-item
          :label-col="{ span: 7 }"
          label="Tài khoản"
          name="userName"
          :rules="[{ required: true, message: 'Tài khoản không được để trống!' }]"
      >
        <a-input v-model:value="formState.userName" placeholder="..."/>
      </a-form-item>

      <a-form-item
          :label-col="{ span: 7 }"
          label="Email"
          name="email"
          :rules="[{ required: true, message: 'Email không được để trống!' }]"
      >
        <a-input type="email" v-model:value="formState.email" placeholder="..."/>
      </a-form-item>

      <a-form-item
          :label-col="{ span: 7 }"
          label="Mật khẩu"
          name="password"
          :rules="[ {required: true,
                  validator: handleTypePassword
            }]"
      >
        <a-input-password v-model:value="formState.password" placeholder="..."/>
      </a-form-item>
      <a-form-item
          :label-col="{ span: 7 }"
          label="Nhập lại mật khẩu"
          name="confirmPassword"
          :rules="[{required: true,
                  validator: handleConfirmPassword
            }]"
      >
        <a-input-password v-model:value="formState.confirmPassword" placeholder="..."/>
      </a-form-item>

      <div class="grid gap-[10px]">
        <a-button class="m-auto block" size="small" type="primary" html-type="submit">Đăng ký</a-button>

        <a-divider style="line-height: 0">
          <NuxtLink to="/dang-nhap" class="float-right">Đã có tài khoản?</NuxtLink>
        </a-divider>

      </div>
    </a-form>
  </div>
</template>
<script setup>
import {reactive, ref} from 'vue';

const formRef = ref();

const formState = reactive({
  userName: '',
  password: '',
  confirmPassword: '',
  remember: true,
})

const onFinish = (values) => {
  console.log('Success:', values);
};

const onFinishFailed = (errorInfo) => {
  console.log('Failed:', errorInfo);
};


const handleTypePassword = (rule, value) => {
  if (value === '') {
    return Promise.reject('Mật khẩu không được để trống!');
  }
  if (value.length < 6) {
    return Promise.reject('Mật khẩu phải có ít nhất 6 ký tự!');
  }
  formRef.value.validateFields('confirmPassword').then(res => {
    console.log('after: ', res)
        .catch(err => {
          console.log('err: ', err)
        })
  });
  return Promise.resolve();
}

const handleConfirmPassword = (rule, value) => {
  if (value === '')
    return Promise.reject('Vui lòng không được để trống!');
  else if (value !== formState.password) {
    return Promise.reject('Mật khẩu không khớp!');
  }
  return Promise.resolve();
};


</script>

<style>
.main_page_content {
  background: white;
}
</style>