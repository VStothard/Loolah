<template>
    <div>
        <div class="flex max-w-lg mx-auto" v-bind:class="{ 'flex-row-reverse': flip }" >
            <div class="flex-1 mr-4">
                <img src="https://source.unsplash.com/random/400x450" class="w-full">
            </div>
            <div class="flex-1">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque sed turpis leo. In hac habitasse platea dictumst. Pellentesque aliquam non magna nec congue. Aenean sagittis ex tincidunt nisl luctus, ac blandit diam maximus. Fusce fermentum, magna ac placerat pulvinar, augue purus pellentesque lacus, vel elementum erat elit non quam. Aenean tincidunt tempor orci eget accumsan. Etiam non nisl et lectus consequat molestie.</p>
                <p>Pellentesque aliquam non magna nec congue. Aenean sagittis ex tincidunt nisl luctus, ac blandit diam maximus. Fusce fermentum, magna ac placerat pulvinar, augue purus pellentesque lacus, vel elementum erat elit non quam. Aenean tincidunt tempor orci eget accumsan. Etiam non nisl et lectus consequat molestie.</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            flip: false
        }
    }
}

//todo: 
// - link flip in storyblok
</script>
