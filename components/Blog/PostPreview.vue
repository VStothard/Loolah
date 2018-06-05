<template>
  <nuxt-link
    :to="id"
    class="border-red border w-full sm:w-1/2 md:w-1/3 no-underline text-black hover:text-grey">
    <article class="post-preview">
      <div
        :style="{backgroundImage: 'url(' + thumbnailImage + ')'}"
        class="w-full h-64 bg-cover mb-4"></div>
      <div class="text-center">
        <p class="text-xs"><span>{{ category.toUpperCase() }}</span> / <span> {{ date }}</span></p>
        <h2 class="text-xl mt-4 mb-2">{{ title.toUpperCase() }}</h2>
        <p class="text-sm">{{ excerpt.toUpperCase() }}</p>
      </div>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    excerpt: {
      type: String,
      required: true
    },
    thumbnailImage: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    },
    category: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    }
  }
};
</script>