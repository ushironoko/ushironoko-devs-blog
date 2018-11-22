<template>
  <section>
    <post-previews :posts="posts" />
  </section>
</template>

<script>
import PostPreviews from '~/components/index/PostPreviews.vue'
import {createClient} from '~/plugins/contentful.js'
const client = createClient()

export default {
  asyncData ({env}) {
    return Promise.all([
      client.getEntries({
        'content_type': env.CTF_BLOG_POST_TYPE_ID,
        order: '-fields.publishDate',
        'limit': 3
      })
    ]).then(([posts]) => {
      return {
        posts: posts.items
      }
    }).catch(console.error)
  },
  components: {
    PostPreviews
  }
}
</script>
