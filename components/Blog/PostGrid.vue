<template>
    <div class="flex flex-wrap justify-between">
        <div v-for="post in posts" :key="post" class="w-full md:w-1/2 lg:w-1/3 max-w-md px-4 mb-6 text-center">
            <img :src="post.thumbnail" :alt="thumbnailAlt" class="w-full mb-4">
            <p class="text-xs mb-4">{{post.category.toUpperCase()}}</p>
            <h2 class="text-md">{{post.title.toUpperCase()}}</h2>
            <!-- <p>{{post.preview}}</p> -->
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: [
                {
                    category: 'Beauty',
                    title: 'Beauty secrets of a pale girl',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Beauty beauty'
                },
                { 
                    category: 'Culture',
                    title: 'A post about nothing in particular',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Nah bra'
                },
                {
                    category: 'Tutorial',
                    title: 'This is how you do it',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Just do it'
                },
                {
                    category: 'Beauty',
                    title: 'Beauty secrets of a pale girl',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Beauty beauty'
                },
                { 
                    category: 'Culture',
                    title: 'A post about nothing in particular',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Nah bra'
                },
                {
                    category: 'Tutorial',
                    title: 'This is how you do it',
                    preview: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non est varius, viverra ipsum eu, condimentum ligula. Nam tempor luctus nibh, vel efficitur nisl facilisis et. Praesent malesuada ex non ex facilisis faucibus. Quisque est velit, pharetra quis elementum eget, blandit quis nibh.',
                    thumbnail: 'https://source.unsplash.com/random/400x480',
                    thumbnailAlt: 'Just do it'
                },
            ]
        }
    }
}
</script>
