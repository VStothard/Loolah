<template>
    <div class="mb-4">
        <input 
            :id="id" :name="name" :type="type" :placeholder="placeholder" 
            v-bind:value="value"
            v-on:input="$emit('input', $event.target.value)"
            v-validate="'required|alpha_spaces'" 
            class="border-t-0 border-l-0 border-r-0 border border-grey-darkest w-full py-4"
        >
        <span class="bg-black text-white text-sm ">{{ errors.first(name) }}</span>
    </div>

</template>

<script>
export default {
    props: {
        id: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        type: {
            type: String,
            required: true
        },
        //value used to make v-model work on components
        value: {
            required: true
        },
        placeholder: {
            type: String,
            required: true
        }
    },
    methods: {

    }
}
</script>
