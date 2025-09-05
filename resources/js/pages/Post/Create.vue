<template>
    <div>
        <form @submit.prevent="submit">
            <label for="">Title</label>
            <input type="text" v-model="form.title">
            <label for="">Slug</label>
            <input type="text" v-model="form.slug">
            <input type="submit" value="Send">
        </form>
    </div>
</template>

<script>
    import {router, useForm} from "@inertiajs/vue3"
    export default{
        setup(){
            const form=useForm({
                title: '',
                slug:'',
            })
            function submit(){
                router.post(route("category.store"),form)
            }

            return {  form, submit  }
        }
    }
</script>