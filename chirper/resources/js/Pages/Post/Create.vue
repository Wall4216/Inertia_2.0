<template>
<div class="w-96 mx-auto pt-8">
    <h1 class="text-lg mb-8">Create</h1>
    <div class="mb-2">
    <Link :href="route('post.index')"  class="text-sky-500 text-sm mb-8">Back</Link>
</div>
    <form @submit.prevent="store">
        <div class="mb-4">
            <input v-model="title" class="w-full rounded-full border-gray-300" type="text" placeholder="title">
        </div>

        <div class="mb-4">
            <textarea v-model="content" class="w-full rounded-full border-gray-300" placeholder="content"></textarea>
        </div>
        <div>
            <button class="ml-auto hover:bg-white hover:350 bg-sky-500 border border-sky-500 p-2 w-32 block rounded-full text-center" type="submit">Store</button>
        </div>
    </form>
</div>
</template>

<script>
import {Link} from "@inertiajs/inertia-vue3";
export default {
    name: "Index",
    components: {
        Link
    },
    data(){
        return {
            title: '',
            content: '',
        }
    },
    methods: {
        store()
        {
            this.$inertia.post('/posts', {title: this.title, content: this.content});
        }
    }
}
</script>

<style scoped>

</style>
