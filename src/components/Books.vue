<template>
    <div>
        <div v-for="book in books" v-bind:key="book">
           <BookItem v-bind:book="book" v-on:del-book="$emit('del-book',book.id)" />
        </div>
    </div>
</template>

<script>
import BookItem from "./BookItem.vue";

export default {
    name:"Books",
    components:{
        BookItem
    },
    props:["books"]
}
</script>

<style scoped>
</style>