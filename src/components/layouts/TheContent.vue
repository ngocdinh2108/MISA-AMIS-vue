<template>
  <div class="content">
    <content-header></content-header>
    <content-body></content-body>
    <content-footer></content-footer>
    <form-detail></form-detail>
    <loading></loading>
  </div>
</template>

<script>
import ContentBody from "../../views/common/ContentBody.vue";
import ContentFooter from "../../views/common/ContentFooter.vue";
import ContentHeader from "../../views/common/ContentHeader.vue";
import FormDetail from "../../views/common/FormDetail.vue";
import Loading from '../../views/common/Loading.vue';
export default {
  components: { ContentHeader, ContentBody, ContentFooter, FormDetail, Loading },
};
</script>,
    FormDetail

<style scoped>
@import url("../../css/content.css");
</style>