<template>
  <nuxt-link
    :to="'/blog/' + id"
    class="w-full sm:w-1/2 md:w-1/3 no-underline text-black hover:text-grey">
    <article class="post-preview">
      <div
        :style="{backgroundImage: 'url(' + thumbnailImage + ')'}"
        class="w-full h-64 bg-cover mb-4"></div>
      <div class="text-center">
        <!-- PostInfo (category / date) -->
        <!-- PostHeadline (category / date) -->
        <slot></slot>
      </div>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    thumbnailImage: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  }
}
</script>