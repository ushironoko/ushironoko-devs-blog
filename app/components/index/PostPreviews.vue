<template>
  <section>
    <el-card v-for="post in posts" :key="post.fields.id">
      <div slot="header" class="clearfix">
        {{ post.fields.title }}
      </div>
      <post-preview-body :body="post.fields.body" />
    </el-card>
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
