<template>
    <div>
        <p class="text-xs"><span>{{ category.toUpperCase() }}</span> / <span>{{date}}</span></p>
        <!--<p class="text-xs"><span>{{ category.toUpperCase() }}</span> / <span> {{ date }}</span></p>-->
    </div>
</template>

<script>
export default {
    props: {
        category: {
            type: String,
            required: true
        },
        date: {
            type: String,
            required: true
        }
    }
}
</script>