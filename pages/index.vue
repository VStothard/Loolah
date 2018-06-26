<template>
  <div>
    <section id="intro" class="container mx-auto give-me-space">
      <ImageWithText />
    </section>
    
    <section id="posts" class="container flex flex-wrap mx-auto give-me-space">
      <post-grid></post-grid>
      <general-button></general-button>
    </section>
  </div>
</template>

<script>

import ImageWithText from "@/components/ImageWithText/ImageWithText"

import PostGrid from "@/components/Blog/PostGrid"
import GeneralButton from "@/components/General/GeneralButton"

export default {
  components: {
    ImageWithText,
    PostGrid,
    GeneralButton
  }
};
</script>

<style>

* {
  box-sizing: border-box;
}
</style>
