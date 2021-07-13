<template>
  <div class="content-header">
    <div class="content-header-left">
      <div class="content-header-left-text">Nhân viên</div>
    </div>
    <div class="content-header-right">
      <div @click="onClickButtonAdd()" class="content-header-right-btn m-btn">
        Thêm mới nhân viên
      </div>
    </div>
  </div>
</template>

<script>
// Import eventBus để sử dụng
import { eventBus } from "../../main.js";
export default {
  /**
   * Sự kiện khi ấn vào nút "Thêm mới nhân viên"
   * CreatedBy: DNDINH (08.07.2021)
   */
  methods: {
    onClickButtonAdd() {
      // 1. Gọi đên API sinh mã mới 
      // 2. Gán mã mới lấy được vào ô Mã nhân viên
      // 3. Gửi sự kiện cho component FormDetail để nó mở lên
      eventBus.$emit("showFormDetail");
    }
  },
};
</script>

<style scoped>
</style>