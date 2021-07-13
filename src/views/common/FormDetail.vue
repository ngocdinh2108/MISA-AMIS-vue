<template>
  <div class="form-detail" :class="{ 'm-hidden': isHide }">
    <div class="form-modal"></div>

    <div class="form-content">
      <div class="form-content-header">
        <div class="form-header-left">
          <div class="form-header-left-heading">Thông tin nhân viên</div>
          <div class="form-header-employee-type">
            <input class="m-checkbox checkbox-employee-type" type="checkbox" />
            Là khách hàng
          </div>
          <div class="form-header-employee-type">
            <input class="m-checkbox checkbox-employee-type" type="checkbox" />
            Là nhà cung cấp
          </div>
        </div>

        <div class="form-header-right">
          <div class="form-header-right-icon icon-help"></div>
          <div @click="closeFormDetail()" class="form-header-right-icon icon-close"></div>
        </div>
      </div>

      <div class="form-content-body">
        <div class="form-content-wrap-row">
          <div class="form-content-wrap">
            <div class="form-content-label">
              Mã <span style="color: red">*</span>
            </div>
            <input class="m-input-w-130 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">
              Tên <span style="color: red">*</span>
            </div>
            <input class="m-input-w-226 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Ngày sinh</div>
            <input class="m-input-w-140 m-input-form" type="date" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Giới tính</div>
            <div class="gender-group-selection">
              <input class="m-radio" type="radio" name="gender" /> Nam
              <input class="m-radio" type="radio" name="gender" /> Nữ
              <input class="m-radio" type="radio" name="gender" /> Khác
            </div>
          </div>
        </div>

        <div class="form-content-wrap-row">
          <div class="form-content-wrap">
            <div class="form-content-label">
              Đơn vị <span style="color: red">*</span>
            </div>
            <input class="m-input-w-384 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Số CMND</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Ngày cấp</div>
            <input class="m-input-w-140 m-input-form" type="date" />
          </div>
        </div>

        <div class="form-content-wrap-row">
          <div class="form-content-wrap">
            <div class="form-content-label">Chức danh</div>
            <input class="m-input-w-384 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Nơi cấp</div>
            <input class="m-input-w-384 m-input-form" type="text" />
          </div>
        </div>

        <div class="form-content-wrap-row form-content-wrap-row-address">
          <div class="form-content-wrap">
            <div class="form-content-label">Địa chỉ</div>
            <input class="m-input-w-816 m-input-form" type="text" />
          </div>
        </div>

        <div class="form-content-wrap-row">
          <div class="form-content-wrap">
            <div class="form-content-label">ĐT di động</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">ĐT cố định</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Email</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>
        </div>

        <div class="form-content-wrap-row">
          <div class="form-content-wrap">
            <div class="form-content-label">Tài khoản ngân hàng</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Tên ngân hàng</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>

          <div class="form-content-wrap">
            <div class="form-content-label">Chi nhánh</div>
            <input class="m-input-w-216 m-input-form" type="text" />
          </div>
        </div>
      </div>

      <div class="form-content-footer">
        <div class="form-content-footer-left">
          <div @click="closeFormDetail()" class="m-btn m-btn-form">Hủy</div>
        </div>

        <div class="form-content-footer-right">
          <div class="m-btn m-btn-form">Cất</div>
          <div class="m-btn m-btn-form m-btn-form-green">Cất và Thêm</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../../main';
export default {
    created () {
        /**
         * Hàm dùng để lắng nghe sự kiện mở form detail được gửi từ các component khác
         * CreatedBy: DNDINH (08.07.2021)
         */
        eventBus.$on("showFormDetail", ()=>{
            this.isHide = false;
        });
    },
    data() {
        return {
            isHide: true
        }
    },
    methods: {
        /**
         * Hàm dùng để đóng form detail
         * CreatedBy: DNDINH (08.07.2021)
         */
        closeFormDetail() {
            this.isHide = true;
        }
    },
};
</script>

<style scoped>
@import url("../../css/formDetail.css");
</style>