<template>
  <section>
    <div>
      <el-card>
        <div slot="header" class="clearfix">
          {{ post.fields.title }}
        </div>
        <post-preview-body :body="post.fields.body" />
      </el-card>
    </div>
  </section>
</template>

<script>
import PostPreviewBody from '~/components/index/PostPreviewBody.vue'
export default {
  props: ['post'],
  components: {
    PostPreviewBody
  }
}
</script>

<style scoped>
  .el-card {
    flex: 1;
    background: #fff;
    border: 2px solid #f5f5f5;
    box-shadow: #e5e5e5 0 5px 5px -3px;
    margin: 0.5vmax 0.5vmax 0.5vmax 0.5vmax;
    overflow: hidden;
    padding: 35px 0px 0px 15px;
    transition: 0.35s;
  }
</style>

