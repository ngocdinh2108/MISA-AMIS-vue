<template>
  <div class="loading" :class="{ 'm-hidden': isHide }">
    <div class="loading-modal"></div>
    <div class="loader"></div>
  </div>
</template>

<script>
import { eventBus } from "../../main";
export default {
  created() {
    /**
     * Lắng nghe sự kiện hiển thị loading từ các component khác
     * CreatedBy: DNDINH (08.07.2021)
     */
    eventBus.$on("showLoading", () => {
      this.isHide = false;
      setTimeout(() => {
        this.isHide = true;
      }, 1000);
    });
  },
  data() {
    return {
      isHide: true,
    };
  },
};
</script>

<style scoped>
@import url("../../css/loading.css");
</style>