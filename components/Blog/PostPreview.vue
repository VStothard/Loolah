<template>
  <div class="w-full md:w-1/3 even-padding-2 mb-4">
    <nuxt-link
      :to="'/blog/' + id">
      <article>
        <div
          :style="{backgroundImage: 'url(' + thumbnailImage + ')'}"
          class="w-full h-96 sm:h-64 md:h-96"
          ></div>
        <div>
          <slot></slot>
        </div>
      </article>
    </nuxt-link>
  </div>
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