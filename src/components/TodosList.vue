<template>
    <div class="todo-list">
        <form action="" class="todo-list-input" @submit.prevent="addTodo">
            <input type="text" v-model="title" placeholder="Enter Todo Item" class="todo-list-inputt"
                   @keyup.enter="addTodo">
            <input type="submit" value="Create Todo" class="btn">
        </form>

        <div v-for="todo in todos" :key="todo.id">
            <SingleTodo :todo="todo" @del-todo="$emit('del-todo',todo.id)" @edit-todo="$emit('edit-todo',todo.id)"/>

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

                incrementToDoId: 4,
            }
        },

        methods: {
            incrementId() {
                this.incrementToDoId++;
            },
            addTodo() {
                //ensure no emty todos added
                if(this.title === ''){
                    return;
                }
                //above can also be. ensure no emty todos added
                // if(this.title.trim().length === 0){
                //     return;
                // }
                // eslint-disable-next-line no-unused-vars
                this.incrementId();
                const newTodo = {
                    id: this.incrementToDoId,
                    title: this.title,
                    completed: false,
                    editing:false
                }
                //send to parent
                this.$emit('add-todo', newTodo);
                this.title = '';
            },


        }

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    form {
        display: flex;
        justify-content: space-between;

        input[type="text"] {
            flex: 10;
            padding: 5px;
        }

        input[type="submit"] {
            flex: 2;
        }


    }

    .todo-list-inputt {


        &:focus {
            outline: chartreuse;
        }
    }

</style>


