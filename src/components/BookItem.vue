<template>
    <div class="book-item">
        <p>
            {{book.title}}
            <button @click="$emit('del-book',book.id)" class="del">x</button>

        </p>
    </div>
</template>

<script>
export default {
   name:"BookItem",
   props:["book"]
}
</script>

<style scoped>
    .book-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .del{
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>