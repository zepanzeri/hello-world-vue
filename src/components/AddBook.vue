<template>
    <div>
        <form @submit="addBook">
            <input type="text" v-model="title" name="title" placeholder="Add a new book">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from "uuid";
export default {
    name:"AddBook",
    data(){
        return{
            title:""
        }
    },
    methods:{
        addBook(e){
            e.preventDefault();
            const newBook={
                id: uuid.v4(),
                title:this.title
            }
            this.$emit("add-book",newBook);
            this.title="";
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        padding: 5px;
    }

    input[type="submit"]{
        flex: 2;
    }
</style>