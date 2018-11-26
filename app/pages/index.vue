<template>
  <section>
    <post-previews :posts="posts" />
  </section>
</template>

<script>
import PostPreviews from '~/components/index/PostPreviews.vue'
import {createClient} from '~/plugins/contentful.js'
const client = createClient()
const POSTS_PRE_PAGE = 100

export default {
  asyncData ({env}) {
    return Promise.all([
      client.getEntries({
        content_type: env.CTF_BLOG_POST_TYPE_ID,
        order: '-fields.publishDate',
        skip: 0,
        limit: POSTS_PRE_PAGE
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
