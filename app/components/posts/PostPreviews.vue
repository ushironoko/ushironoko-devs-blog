<template>
  <section>
    <div>
      <el-card>
        <div slot="header" class="clearfix title">
          {{ post.fields.title }}
        <time>{{ displayCreatedAt }}</time>
        </div>
        <post-preview-body :body="post.fields.body" />
      </el-card>
    </div>
  </section>
</template>

<script>
import PostPreviewBody from '~/components/posts/PostPreviewBody.vue'
import dateformat from 'dateformat'

export default {
  props: ['post'],
  computed: {
    displayCreatedAt () {
      return dateformat(new Date(this.post.sys.createdAt), 'yyyy-mm-dd')
    }
  },
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
    padding: 35px 0px 0px 0px;
    transition: 0.35s;
    width: 100%;
    max-width: 800px;
  }

  .title {
    font-size: 30px;
  }
</style>

