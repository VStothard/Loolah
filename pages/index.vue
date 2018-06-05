<template>
  <section id="posts" class="border border-blue container flex flex-wrap mx-auto">
    <PostPreview
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :excerpt="post.previewText"
      :thumbnailImage="post.thumbnailUrl"
      :id="post.id"
      :category="post.category" 
      :date="post.date"
      class="border border-black inline-block p-4"
      />
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
          title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "https://source.unsplash.com/random",
          id: "P01",
          category: 'Beauty',
          date: '25.05.18'
        },
        {
          title: "Amet, consectetur adipiscing elit",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "https://source.unsplash.com/random",
          id: "P02",
          category: 'Tech',
          date: '25.05.18'
        },
        {
          title: "Ipsum dolor sit amet, consectetur adipiscing",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "https://source.unsplash.com/random",
          id: "P03",
          category: 'Art',
          date: '25.05.18'
        },
        {
          title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "https://source.unsplash.com/random",
          id: "P04",
          category: 'Culture',
          date: '25.05.18'
        },
        {
          title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "https://source.unsplash.com/random",
          id: "P05",
          category: 'History',
          date: '25.05.18'
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
