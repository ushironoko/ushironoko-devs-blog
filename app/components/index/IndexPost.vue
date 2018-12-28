<template>
  <div>
    <div>
      <time>{{ displayCreatedAt }}</time>
    </div>
    <div class="post-title">
      {{ post.fields.title }}
    </div>
    <div class="post-description">
      {{ post.fields.description }}
    </div>
  </div>
</template>

<script>
import dateformat from 'dateformat'

export default {
  props: {
    post: {
      required: true
    }
  },
  computed: {
    displayCreatedAt () {
      return dateformat(new Date(this.post.sys.createdAt), 'yyyy-mm-dd')
    }
  }
}
</script>

<style scoped>
  .post-title {
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    font-size: 26px;
  }
  .post-description {
    padding-top: 10px;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    font-size: 12px;
    color: darkgrey;
  }
</style>
