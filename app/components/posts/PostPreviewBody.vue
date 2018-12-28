<template>
  <div v-html="$md.render(body)"></div>
</template>

<script>
export default {
  props: ['body']
}
</script>
