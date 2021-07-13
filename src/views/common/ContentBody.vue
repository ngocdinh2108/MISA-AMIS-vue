<template>
  <div class="content-body">
    <div class="content-body-filter">
      <div class="content-filter-search">
        <input
          class="content-filter-search-input m-input"
          type="text"
          placeholder="Tìm theo mã, tên nhân viên"
        />
        <div class="content-filter-search-icon icon-search"></div>
      </div>
      <div
        @click="onClickButtonRefresh()"
        class="content-filter-icon icon-refresh"
      ></div>
      <div class="content-filter-icon icon-excel"></div>
    </div>

    <div class="content-body-grid">
      <table border="0" cellspacing="0">
        <thead>
          <tr>
            <th
              class="m-align-center column-fixed-left check-all"
              style="min-width: 28px"
            >
              <input class="m-checkbox" type="checkbox" />
            </th>
            <th style="min-width: 130px">MÃ NHÂN VIÊN</th>
            <th style="min-width: 230px">TÊN NHÂN VIÊN</th>
            <th style="min-width: 100px">GIỚI TÍNH</th>
            <th class="m-align-center" style="min-width: 130px">NGÀY SINH</th>
            <th style="min-width: 180px">SỐ CMND</th>
            <th style="min-width: 230px">CHỨC DANH</th>
            <th style="min-width: 230px">TÊN ĐƠN VỊ</th>
            <th style="min-width: 130px">SỐ TÀI KHOẢN</th>
            <th style="min-width: 230px">TÊN NGÂN HÀNG</th>
            <th style="min-width: 230px">CHI NHÁNH TK NGÂN HÀNG</th>
            <th
              class="m-align-center column-fixed-right column-function"
              style="min-width: 100px"
            >
              CHỨC NĂNG
            </th>
          </tr>
        </thead>

        <tbody>
          <tr v-for="(employee) in employees" :key="employee.EmployeeId">
            <td class="m-align-center column-fixed-left">
              <input class="m-checkbox" type="checkbox" />
            </td>
            <td>{{employee.EmployeeCode}}</td>
            <td>{{employee.FullName}}</td>
            <td>{{employee.Gender}}</td>
            <td class="m-align-center">{{employee.DateOfBirth}}</td>
            <td>164605328</td>
            <td>Fresher</td>
            <td>Misa</td>
            <td>05501116666678</td>
            <td>MB Bank</td>
            <td>Chi nhánh Hai Bà Trưng</td>
            <td class="column-fixed-right m-align-center">Sửa</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../../main';
import axios from 'axios'
export default {
  data() {
    return {
      employees: []
    }
  },
  created () {
    this.getDataTable();
  },
  methods: {
    /**
     * Sự kiện khi ấn vào nút nạp lại
     * CreatedBy: DNDINH (08.07.2021)
     */
    onClickButtonRefresh() {
      // 1. Nạp lại dữ liệu của table
      // 2. Gọi component loading để nó hiện lên trong 1s
      eventBus.$emit("showLoading");
    },

    /**
     * Sự kiện binding dữ liệu vào grid
     * CreatedBy: DNDINH (08.07.2021)
     */
    getDataTable(){
      // 1. Dùng axios để gọi API lấy tất cả thông tin của bảng employee
      axios.get("http://cukcuk.manhnv.net/v1/Employees")
        .then((res) => {
          this.employees = res.data;
          console.log(res)
        }).catch((res)=>{
          console.log(res)
        })
      // 2. Format ngày sinh, giới tính 
    }
  },
};
</script>

<style scoped>
@import url("../../css/grid.css");
</style>