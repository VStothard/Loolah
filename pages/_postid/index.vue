<template>
    <div id="post">
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
            return {
                title: res.data.story.content.title,
                body: res.data.story.content.body
            }
        })
    }
}
</script>