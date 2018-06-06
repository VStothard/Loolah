<template>
    <section id="blog-page" class="container mx-auto">
        <!--back to home, eventualy, back to previous page -->
    
        <div class="single flex flex-wrap">
            <div class="w-full">
                <img :src="post.featureImg" class="w-full h-auto">
            </div>
            <div class="w-full sm:w-full md:w-1/6">
                <p>X</p>
                <p>X</p>
                <p>X</p>
            </div>
            <div class="w-full sm:w-full md:w-5/6">
                <h1>{{post.heading}}</h1>
                <p>{{post.content}}</p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data () {
        return {
            post: {
                featureImg: 'https://source.unsplash.com/random/1200x400',
                heading: 'This is where your blogs will go',
                content: 'Hello, this is the content you asked me for'
            }
        }
    }
    
    // props: {
    //     blogTitle: {
    //         type: String,
    //         required: true
    //     },
    //     blogContent: {
    //         type: String,
    //         required: true
    //     },
    //     blogFeatureImg: {
    //         type: String,
    //         required: true
    //     }
    // }
}
</script>

