<template>
  <a-table
      :loading="tblLoading"
      :columns="tblHeaders"
      :pagination="false"
      @change="tblChange"
      :data-source="tblData" bordered>
    <template #bodyCell="{ column, record }">
      <template v-if="column.dataIndex === 'operation'">
        <a-button type="primary" size="small" @click="registerCourse">Đăng ký</a-button>
      </template>

      <template v-if="column.dataIndex === 'course'">
        <NuxtLink to="/saa" class="flex items-center gap-[3px]">
          {{ record.course }}
          <eye-outlined class="text-[9px]"/>
        </NuxtLink>
      </template>

    </template>
  </a-table>
</template>

<script setup>
import {
  EyeOutlined
} from "@ant-design/icons-vue";
import {ref} from "vue";


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
    responsive: ['md'],
  },
  {
    title: 'Tình Trạng',
    dataIndex: 'status',
    align: 'center',
    key: 'status',
    responsive: ['md'],
  },
  {
    title: '',
    dataIndex: 'operation',
    align: 'center',
    key: 'operation',
  }
];
const tblLoading = ref(false);

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