<template>
  <section id="posts" class="container flex flex-wrap mx-auto">
    <PostPreview
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :excerpt="post.previewText"
      :thumbnailImage="post.thumbnailUrl"
      :id="post.id"
      class="inline-block p-4"
      >
        <!-- <PostInfo 
          :category="post.category"
          :date="post.date"
        /> -->
        <PostHeadline
          :title="post.title"
          :previewText="post.previewText"
          />
      </PostPreview>
  </section>
</template>

<script>

import PostPreview from "@/components/Blog/PostPreview"
import PostInfo from '@/components/Blog/PostInfo'
import PostHeadline from '@/components/Blog/PostHeadline'

export default {
  components: {
    PostPreview,
    PostInfo,
    PostHeadline
  },
  asyncData(context) {
    return context.app.$storyapi.get('cdn/stories', {
      version: "draft",
      starts_with: "blog/"
    }).then(res => {
      console.log(res.data.stories);
      return {
        posts: res.data.stories.map(bp => {
          return {
            id: bp.slug,
            title: bp.content.title,
            thumbnailUrl: bp.content.thumbnail,
            previewText: bp.content.description,

          }
        })
      }
    });
  }
  // data() {
    // return {
    //   posts: [
    //     {
    //       title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
    //       previewText: "This will be awesome, don't miss it!",
    //       thumbnailUrl:
    //         "https://source.unsplash.com/random",
    //       id: "P01",
    //       category: 'Beauty',
    //       date: '25.05.18'
    //     },
    //     {
    //       title: "Amet, consectetur adipiscing elit",
    //       previewText: "This will be awesome, don't miss it!",
    //       thumbnailUrl:
    //         "https://source.unsplash.com/random",
    //       id: "P02",
    //       category: 'Tech',
    //       date: '25.05.18'
    //     },
    //     {
    //       title: "Ipsum dolor sit amet, consectetur adipiscing",
    //       previewText: "This will be awesome, don't miss it!",
    //       thumbnailUrl:
    //         "https://source.unsplash.com/random",
    //       id: "P03",
    //       category: 'Art',
    //       date: '25.05.18'
    //     },
    //     {
    //       title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
    //       previewText: "This will be awesome, don't miss it!",
    //       thumbnailUrl:
    //         "https://source.unsplash.com/random",
    //       id: "P04",
    //       category: 'Culture',
    //       date: '25.05.18'
    //     },
    //     {
    //       title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
    //       previewText: "This will be awesome, don't miss it!",
    //       thumbnailUrl:
    //         "https://source.unsplash.com/random",
    //       id: "P05",
    //       category: 'History',
    //       date: '25.05.18'
    //     }
    //   ]
    // };
  // }
};
</script>

<style>

* {
  box-sizing: border-box;
}
</style>
