<template>
    <div class="mx-auto block mb-6">
        <a href="#" class="no-underline bg-black text-white p-4 border-none hover:bg-grey-darkest cursor-pointer">VIEW MORE</a>
    </div>
</template>

<script>
export default {
    props: {
        buttonText: {
            type: String,
            required: true
        }
    }
}
</script>

