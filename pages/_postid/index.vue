<template>
    <div id="post" v-editable="blok">
        <div class="thumbnail"></div>
        <h1>{{title}}</h1>
        <p>{{body}}</p>
    </div>
</template>

<script>
export default {
    asyncData(context) {
        return context.app.$storyapi
        .get("cdn/stories/blog/" + context.params.postid, {
            version: "draft"
        }).then(res => {
            console.log(1000, res.data.story.content);
            return {
                blok: res.data.story.content,
                title: res.data.story.content.title,
                body: res.data.story.content.body
            }
        })
    },
    //mounted runs on the client, vs created which runs on the serve
    mounted() {
        this.$storyblok.init();
        this.$storyblok.on('change', () => {
            location.reload(true);
        })
    }
}
</script>