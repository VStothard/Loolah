<template>
  <div>
    <!-- render data of the person -->
    <!-- <h1>{{ person.fields.name }}</h1> -->
    <!-- render blog posts -->
    <ul>
      <li v-for="post in posts" :key="post.id">
        {{ post.fields.title }}
        {{ post.fields.description }}
        {{ post.fields.body }}
        {{ post.fields.slug }}
      </li>
    </ul>
    <section id="intro" class="container mx-auto give-me-space">
      <ImageWithText />
    </section>
    
    <section id="posts" class="container flex flex-wrap mx-auto give-me-space">
      <post-grid></post-grid>
      <general-button button-text="VIEW MORE" button-link="www.google.com"></general-button>
    </section>
  </div>
</template>

<script>
import {createClient} from '~/plugins/contentful.js'

import ImageWithText from "@/components/ImageWithText/ImageWithText"
import PostGrid from "@/components/Blog/PostGrid"
import GeneralButton from "@/components/General/GeneralButton"

const client = createClient()

export default {
  components: {
    ImageWithText,
    PostGrid,
    GeneralButton
  },
  // `env` is available in the context object
  asyncData ({env}) {
    return Promise.all([
      // fetch the owner of the blog
      client.getEntries({
        'sys.id': env.CTF_PERSON_ID
      }),
      // fetch all blog posts sorted by creation date
      client.getEntries({
        'content_type': env.CTF_BLOG_POST_TYPE_ID,
        order: '-sys.createdAt'
      })
    ]).then(([entries, posts]) => {
      // return data that should be available
      // in the template
      return {
        person: entries.items[0],
        posts: posts.items
      }
    }).catch(console.error)
  },
  created() {
    // fetch all blog posts sorted by creation date
    console.log('created', 1000);
    client.getEntries({
      'content_type': 'blogPost',
      order: '-sys.createdAt'
    }).then(
      (res) => {
        console.log(res);
      }
    ).catch(console.error);
  }
};
</script>

<style>

* {
  box-sizing: border-box;
}
</style>
