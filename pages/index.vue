<template>
  <div id="home_page" class="bg-white">

    <SlideSection/>

    <section
        class="commitment_section w-full h-[50px] text-center items-center grid grid-cols-4 divide-x divide-gray-400">
      <div class="bg-[#2b8df2] h-full flex gap-[3px] items-center justify-center font-bold text-white">
        <user-outlined/>
        89+ Học Viên
      </div>
      <div class="bg-[#2b8df2] h-full flex gap-[3px] items-center justify-center font-bold text-white">
        Đội ngũ giáo viên giàu kinh nghiệm
      </div>
      <div class="bg-[#2b8df2] h-full flex gap-[3px] items-center justify-center font-bold text-white">
        <profile-outlined/>
        Hỗ trợ 24/7
      </div>
      <div class="bg-[#2b8df2] h-full flex gap-[3px] items-center justify-center font-bold text-white">
        <desktop-outlined/>
        Học online, offline học mọi lúc mọi nơi
      </div>
    </section>

    <section class="list_courses py-[30px] w-[1200px] m-auto">
      <h3 class="text-2xl font-bold text-center">
        Danh sách khóa học
        <span class="block bg-gray-300 h-[1px] w-[120px] m-auto mt-[10px]"/>
      </h3>

      <div class="grid grid-cols-3 gap-[40px] w-fit m-auto mt-[20px]">
        <CourseCard/>
        <CourseCard/>
        <CourseCard/>
      </div>
    </section>

    <section class="classes_section m-auto bordered pt-[20px] w-[1400px]">
      <h3 class="text-2xl font-bold text-center">
        Danh sách lớp đang mở
        <span class="block bg-gray-300 h-[1px] w-[120px] m-auto mt-[10px]"/>
      </h3>

      <div class="p-[10px] max-w-[1200px] m-auto">
        <ClassTable/>
      </div>
    </section>

    <section class="teachers_section py-[30px] w-[1200px] m-auto pt-[20px]">
      <h3 class="text-2xl font-bold text-center">
        Đội ngũ giáo viên
        <span class="block bg-gray-300 h-[1px] w-[120px] m-auto mt-[10px]"/>
      </h3>

      <div>
        <a-carousel
            :slidesToShow="5"
            :slidesToScroll="1"
            :speed="500"
            dotsClass="teacher_dots_slick"
            :draggable="true"
            :autoplay="false"
            :focusOnSelect="true"
            :infinite="true"
        >
          <div class="p-[20px]">
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto hover:scale-[1.1] duration-300 ease-in-out"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div class="p-[20px]">
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto hover:scale-[1.1] duration-300 ease-in-out"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div class="p-[20px]">
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto hover:scale-[1.1] duration-300 ease-in-out"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div>
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div>
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div>
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div>
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>

          <div>
            <a href="/99as">
              <img class="rounded-full w-[200px] h-[200px] m-auto"
                   src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
              <p class="text-black mt-[10px] text-center">
                <span class="font-bold">Nguyễn Văn A</span>
                <br>
                <span class="text-gray-400">
                  Giáo viên tiếng Anh
                </span>
              </p>
            </a>
          </div>
        </a-carousel>

      </div>

    </section>

    <section class="py-[30px] bg-white m-auto ">
      <h3 class="text-2xl font-bold text-center">
        Đánh giá của học viên
        <span class="block bg-gray-300 h-[1px] w-[120px] m-auto mt-[10px]"/>
      </h3>

      <div class="max-w-[1400px] m-auto px-[20px] grid grid-cols-6">
        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>

        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>

        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>
        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>
        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>
        <div class="review_item bordered border-[1px] max-w-[200px] p-[10px] text-center rounded">
          <img class="rounded-full w-[120px] h-[120px] m-auto"
               src="https://theme.hstatic.net/200000322155/1000700210/14/home_client_image_1.png?v=1074">
          <a-rate :value="5" style="width: fit-content; margin: auto; display: block !important;" />
          <p class="text-[#5A5A5A] text-[13px] font-bold mt-[10px] text-center m-0">
            Học viên 1 <br>
            Khóa: ass, Lớp: 1ns
          </p>
          <p class="text-[#5a5a5a]">
            Minh rat vui khi duoc tham gia khoa hoc nay!
          </p>

        </div>
      </div>

    </section>


    <section class="py-[30px] m-auto bg-[#f3fffb] ">

      <h3 class="text-center text-2xl font-bold">Đăng ký tư vấn ngay</h3>
      <ContactForm />
    </section>


  </div>
</template>

<script setup>
import {
  DesktopOutlined,
  UserOutlined,
  ProfileOutlined
} from "@ant-design/icons-vue";

import SlideSection from "../components/home_page/SlideSection";
import CourseCard from "../components/course_card/CourseCard";
import ContactForm from "../components/ContactForm";
import ClassTable from "../components/ClassTable";


useMeta({
  title: "home",
});
</script>

<style>

.teachers_section .teacher_dots_slick {
  bottom: -20px;
}


.teachers_section .teacher_dots_slick li > button {
  background-color: #faad14;
}

.teachers_section .teacher_dots_slick li.slick-active > button {
  background-color: #FFC107;
}

</style>