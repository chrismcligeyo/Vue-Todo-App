<template>
    <div class="todo-list">
        <form action="" class="todo-list-input">
            <input type="text" v-model="title" placeholder="Enter Todo Item" class="todo-list-inputt">
            <input type="submit" value="Create Todo" class="btn">
        </form>

        <div v-for="todo in todos" :key="todo.id">
            <SingleTodo :todo="todo"/>

        </div>

    </div>
</template>

<script>
    import SingleTodo from "./SingleTodo";

    export default {
        name: 'TodosList',

        props: ["todos"],
        components: {
            SingleTodo,
        },

        data() {
            return {
                title: "",
                /*   todo: {
                       id: 1,
                       title: 'Walk the dog',
                       completed: false
                   }*/

            }
        },

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    form{
        display: flex;
        justify-content: space-between;

        input[type="text"]{
            flex: 10;
            padding: 5px;
        }

        input[type="submit"]{
            flex: 2;
        }




    }

    .todo-list-inputt{




        &:focus{
            outline: chartreuse;
        }
    }

</style>


