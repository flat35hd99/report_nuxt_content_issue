<template>
  <div>
    <ul>
      <li
        v-for="document in documents"
        :key="document.slug"
      >
        <nuxt-link :to="document.path">{{ document.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const documents = await $content({ deep: true }).fetch()
    return {
      documents
    }
  }
}
</script>