<template>
  <div class="w-full md:w-1/3 even-padding-2 mb-4">
    <nuxt-link
      :to="'/blog/' + id">
      <article>
        Here is a post
      </article>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    }
  }
}
</script>