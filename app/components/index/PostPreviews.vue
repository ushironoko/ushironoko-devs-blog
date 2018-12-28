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
