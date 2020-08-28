<template>
  <div>
    <nuxt-content :document="document" />
    <hr>content object is below <hr>
    {{ document }}
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const document = await $content(params.slug).fetch()
      return { document }
  }
}
</script>
