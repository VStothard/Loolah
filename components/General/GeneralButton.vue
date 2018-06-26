<template>
    <div class="bg-black hover:bg-grey-darkest cursor-pointer p-4 mx-auto block give-me-space">
        <a :href="buttonLink" class="no-underline text-white border-none">{{buttonText}}</a>
    </div>
</template>

<script>
export default {
    props: {
        buttonText: {
            type: String,
            required: true
        },
        buttonLink: {
            type: String,
            required: true
        }
    }
}
</script>

