<template>
  <div>
    <section id="intro" class="container mx-auto give-me-space">
      <ImageWithText />
    </section>
    
    <section id="posts" class="container flex flex-wrap mx-auto give-me-space">
      <PostPreview
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        :excerpt="post.previewText"
        :thumbnailImage="post.thumbnailUrl"
        :id="post.id"
        class="inline-block"
        >
      <PostHeadline
        :title="post.title"
        :previewText="post.previewText"
        />
      </PostPreview>
    </section>
  </div>
</template>

<script>

import ImageWithText from "@/components/ImageWithText/ImageWithText"

import PostPreview from "@/components/Blog/PostPreview"
import PostInfo from '@/components/Blog/PostInfo'
import PostHeadline from '@/components/Blog/PostHeadline'

export default {
  components: {
    ImageWithText,
    PostPreview,
    PostInfo,
    PostHeadline
  },
  asyncData(context) {
    return context.app.$storyapi.get('cdn/stories', {
      version: process.env.NODE_ENV == "production" ? "published" : "draft",
      starts_with: "blog/"
    }).then(res => {
      // console.log(1000, res.data);
      return {
        // blok: res.data.stories.content,
        posts: res.data.stories.map(bp => {
          return {
            blok: bp.content,
            id: bp.slug,
            title: bp.content.title,
            thumbnailUrl: bp.content.thumbnail,
            previewText: bp.content.description,

          }
        })
      }
    });
  },
};
</script>

<style>

* {
  box-sizing: border-box;
}
</style>
