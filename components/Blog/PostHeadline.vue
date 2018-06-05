<template>
    <div>
        <h2 class="text-xl my-4">{{ title.toUpperCase() }}</h2>
        <p class="text-xs">{{ previewText.toUpperCase() }}</p>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        previewText: {
            type: String,
            required: true
        }
    }
}
</script>
