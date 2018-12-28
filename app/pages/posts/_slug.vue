<template>
  <PostPreviews :post="post" :includes="includes"/>
</template>

<script>
import PostPreviews from '~/components/posts/PostPreviews'
import {createClient} from '~/plugins/contentful.js'

const client = createClient()
export default {
  asyncData ({ env, params, error }) {
    const select = [
      'sys.createdAt',
      'fields.title',
      'fields.slug',
      'fields.body',
      'fields.heroImage'
    ]
    return client.getEntries({
        content_type: env.CTF_BLOG_POST_TYPE_ID,
        select: select.join(','),
        'fields.slug': params.slug,
        limit: 1
    }).then(({ items, includes }) => {
      if (items.length === 0) {
        return error({ statusCode: 404 })
      }
      return {
        post: items[0],
        includes
      }
    }).catch(error => {
      return error({ statusCode: 500 })
    })
  },
  components: { PostPreviews }
}
</script>
