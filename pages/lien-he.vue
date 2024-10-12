<template>
  <div id="contact" class="bg-white">
<!--    <div class="bg-[#1976d2] p-[100px] text-3xl text-center">-->
<!--      <h1 class="text-white font-bold">-->
<!--        Liên hệ tư vấn miễn phí các khóa học của chúng tôi-->
<!--      </h1>-->
<!--    </div>-->

    <div class="max-w-[600px] m-auto">
      <div class="text-center m-auto pt-[50px]">
        <h2 class="text-3xl font-bold">Đăng ký tư vấn và hỗ trợ </h2>
        <p class="text-xl">
          Vui lòng điền các thông tin liên hệ, HOCPTE sẽ liên hệ và giải đáp các thắc mắc của bạn trong thời gian sớm
          nhất.
        </p>
      </div>

      <ContactForm />
    </div>

    <div class="more_info w-full bg-[#f3f9ff] py-[40px] px-[50px]"
         style="border-top: 1px solid #e1f5fe; border-bottom: 1px solid #e1f5fe">

      <div class="p-[20px] text-2xl text-center">
        <h1 class="font-bold">
          Liên hệ với HOCPTE
        </h1>
        <div class="inline-block w-[100px] rounded h-[5px] bg-[#00b0ff]"></div>
      </div>

      <div class="max-w-[1000px] m-auto lg:flex">
        <ul class="w-1/2 list_content">
          <li class="relative pl-[20px]">
            <h2 class="text-sm font-bold inline-block">Địa chỉ: </h2>
            <p class="inline-block pl-[5px]">
              123 Trần Hưng Đạo, Phường 5, Quận 5, TP. Hồ Chí Minh
            </p>
          </li>

          <li class="relative pl-[20px] my-[10px]">
            <h2 class="text-sm font-bold inline-block">Điện thoại:</h2>
            <p class="inline-block pl-[5px]">
              0123456789
            </p>
          </li>

          <li class="relative pl-[20px]">
            <h2 class="text-sm font-bold inline-block">Email:</h2>
            <p class="inline-block pl-[5px]">
              0123456789
            </p>
          </li>
        </ul>

        <div>
          <h2 class="text-sm font-bold text-center">Kết nối với HOCPTE trên mạng xã hội</h2>
          <ul class="flex gap-[10px] m-auto w-fit">
            <li>
              <google-outlined/>
            </li>
            <li>
              <twitter-outlined/>
            </li>
            <li>
              <youtube-outlined/>
            </li>
            <li>
              <instagram-outlined/>
            </li>
            <li>
              <facebook-outlined/>
            </li>
          </ul>
        </div>

      </div>
    </div>

  </div>

</template>

<script setup>
import {reactive} from "vue";
import {
  GoogleOutlined,
  TwitterOutlined,
  YoutubeOutlined,
  InstagramOutlined,
  FacebookOutlined
} from "@ant-design/icons-vue";
import ContactForm from "../components/ContactForm";




</script>

<style>


#contact .list_content li:before {
  content: "";
  width: 8px;
  height: 8px;
  border-radius: 50%;
  position: absolute;
  top: 8px;
  left: 4px;
  background: #00b0ff;
}
</style>