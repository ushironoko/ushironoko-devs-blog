<template>
  <section>
    <div>
      <el-card v-for="post in posts" :key="post.fields.id">
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
  props: ['posts'],
  components: {
    PostPreviewBody
  }
}
</script>

<style>
.pagenation{
  padding: 16px 0;
  display: flex;
  justify-content: center;
  align-items: flex-start;
}
</style>
