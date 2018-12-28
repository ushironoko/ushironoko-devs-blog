<template>
  <section>
    <IndexPosts :posts="posts" />
  </section>
</template>

<script>
import IndexPosts from '~/components/index/IndexPosts.vue'
import {createClient} from '~/plugins/contentful.js'

const client = createClient()

export default {
  asyncData ({env}) {
    const select = [
      'sys.createdAt',
      'fields.title',
      'fields.slug',
      'fields.description'
    ]
    return Promise.all([
      client.getEntries({
        content_type: env.CTF_BLOG_POST_TYPE_ID,
        order: '-sys.createdAt',
        select: select.join(',')
      })
    ]).then(([posts]) => {
      return {
        posts: posts.items
      }
    }).catch(console.error)
  },
  components: {
    IndexPosts
  }
}
</script>
