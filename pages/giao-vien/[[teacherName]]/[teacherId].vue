<template>
  <div id="teacher_profile" class="max-w-[800px] m-auto bg-white rounded">
    <a-page-header
        style="padding: 10px 0"
        :breadcrumb="breadCrumbConfig"
    >
      <div class="divide-y grid gap-[20px]">
        <div class="text-center mt-[20px] gap-[20px]">
          <img class="rounded h-160px w-[160px] m-auto"
               src="https://avatars.preply.com/i/logos/i/logos/avatar_ei1b93rlo1u.jpg?d=160x160&f=webp">
          <h1 class="font-bold text-2xl m-0">Sophie P.
          </h1>
        </div>

        <section class="description px-[20px]">
          <h3 class="text-xl pt-[20px]">Giới thiệu</h3>
          <div class="desc_content">
            Hi there, my name is Jon!

            I'm a qualified teacher from the UK and a native speaker. I hold a CertTesol qualification (one of the
            highest
            English qualifications) from the internationally recognized Oxford International School in London.

            I have worked with young learners and adults from across the world, including: Chile, China, Saudi Arabia,
            Turkey and Japan.

            I am patient, understanding and recognize how difficult it can be to learn a new language!

            Preparing for IELTS? Hoping to improve your grammar? Learn Academic English for university study? I have
            successfully supported students in all 3 of these areas.

            Lessons are focused around conversation, grammar and most importantly having fun!

            As a tutor I use a communicative approach in lessons, ...
          </div>
        </section>

        <section class=" px-[20px]">
          <h3 class="text-xl pt-[20px]">Kinh nghiệm giảng dạy</h3>
        </section>

        <section class=" px-[20px]">
          <h3 class="text-xl pt-[20px]">Chứng chỉ</h3>
        </section>

        <section class=" px-[20px]">
          <h3 class="text-xl pt-[20px]">Sở thích</h3>
        </section>

        <client-only>
          <div class="related_course_with_teacher px-[20px]">
            <h3 class="text-xl pt-[20px]">
              Các lớp học đang dạy
            </h3>
            <a-table
                :loading="tblLoading"
                :columns="tblHeaders"
                :pagination="tblPageConfig"
                @change="tblChange"
                :data-source="tblData" bordered>
              <template #bodyCell="{ column, record }">
                <template v-if="column.dataIndex === 'operation'">
                  <a-button type="primary" size="small" @click="registerCourse">Đăng ký</a-button>
                </template>

                <template v-if="column.dataIndex === 'course'">
                  <NuxtLink to="/saa">
                    {{ record.course }}
                    <eye-outlined class="text-[11px]"/>
                  </NuxtLink>
                </template>

              </template>
            </a-table>
          </div>
        </client-only>
      </div>
    </a-page-header>
  </div>
</template>


<script setup>
import {
  EyeOutlined
} from "@ant-design/icons-vue";

import {ref} from "vue";

const breadCrumbConfig = {
  routes: [
    {
      path: "/",
      breadcrumbName: "Trang chủ",
    },
    {
      path: "/danh-sach-giao-vien",
      breadcrumbName: "Giáo viên",
    },
    {
      path: "#",
      breadcrumbName: "Sophie P",
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

const tblHeaders = [
  {
    title: 'Lớp học',
    dataIndex: 'className',
    align: 'center',
    key: 'name',
  },
  {
    title: 'Khóa học',
    dataIndex: 'course',
    align: 'center',
    key: 'name',
  },
  {
    title: 'Giá',
    dataIndex: 'price',
    align: 'center',
    key: 'price',
  },
  {
    title: 'Thời gian bắt đầu',
    dataIndex: 'startDate',
    align: 'center',
    key: 'time',
  },
  {
    title: 'Trạng thái',
    dataIndex: 'status',
    align: 'center',
    key: 'status',
  },
  {
    title: '',
    dataIndex: 'operation',
    align: 'center',
    key: 'operation',
  }
];
const tblLoading = ref(false);
const tblPageConfig = ref({
  current: 1,
  pageSize: 10,
  total: 102,
  showSizeChanger: false
});

// write tblData
const tblData = [
  {
    key: '1',
    className: 'Lớp 1',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  },
  {
    key: '2',
    className: 'Lớp 2',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  },
  {
    key: '3',
    className: 'Lớp 3',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  },
  {
    key: '4',
    className: 'Lớp 4',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  },
  {
    key: '5',
    className: 'Lớp 5',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  },
  {
    key: '6',
    className: 'Lớp 6',
    course: 'Tiếng Anh giao tiếp',
    description: 'Lớp học tiếng Anh giao tiếp',
    price: '100.000',
    startDate: '2021-10-10',
    status: 'Đang diễn ra',
    operation: 'Đăng ký',
  }
];

const tblChange = (pagination, filters, sorter) => {
  tblLoading.value = true;
  console.log('params', pagination, filters, sorter);
  tblPageConfig.value = {
    ...pagination,
    total: 62
  };
};

const registerCourse = () => {
  console.log('register course');
}

</script>