<template>
  <section id="posts">
    <PostPreview
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :excerpt="post.previewText"
      :thumbnailImage="post.thumbnailUrl"
      :id="post.id" />
  </section>
</template>

<script>
import PostPreview from "@/components/Blog/PostPreview";
export default {
  components: {
    PostPreview
  },
  data() {
    return {
      posts: [
        {
          title: "A New Beginning",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "http://www.healthyfood.co.uk/wp-content/uploads/2015/01/Cherry-tomato-bocc-olive-basil-pasta.jpg",
          id: "a-new-beginning"
        },
        {
          title: "A Second Beginning",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "http://www.healthyfood.co.uk/wp-content/uploads/2015/01/Cherry-tomato-bocc-olive-basil-pasta.jpg",
          id: "a-second-beginning"
        }
      ]
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
</style>
