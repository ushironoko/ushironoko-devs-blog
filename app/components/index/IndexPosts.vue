<template>
  <section>
    <div class="contents" v-for="post in posts" :key="post.items">
      <nuxt-link :to="{ name: 'posts-slug', params: { slug: post.fields.slug }}" style="text-decoration: none; color :black;">
        <index-post :post="post" />
      </nuxt-link>
    </div>
  </section>
</template>

<script>
import IndexPost from '~/components/index/IndexPost.vue'
import dateformat from 'dateformat'

export default {
  props: {
    posts: {
      required: true
    }
  },
  components: {
    IndexPost
  }
}
</script>

<style scoped>
  .contents {
    flex: 1;
    background: #fff;
    border: 2px solid #f5f5f5;
    box-shadow: #e5e5e5 0 5px 5px -3px;
    display: inline-flex;
    height: 275px;
    margin: 0.5vmax 0.5vmax 0.5vmax 0.5vmax;
    overflow: hidden;
    padding: 35px 0px 0px 15px;
    transition: 0.35s;
    width: 360px;
  }
</style>
