<template>
    <div>

        <div class="single-todo-item">
           <p>
               <input type="checkbox">
               {{todo.title}}</p>
            <div class="del-single-todo-item">
               &times; <!-- x symbol html entity-->
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'SingleTodo',
        data() {
            return {

             /*   todo: {
                    id: 1,
                    title: 'Walk the dog',
                    completed: false
                }*/

            }
        },
        props: ["todo"],
        components: {},
        methods: {}

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .single-todo-item {
        display: flex;
        background: #f4f4f4;
        padding: 5px;
        border-bottom: dotted 1px #cccccc;
        justify-content: space-between;
    }

    .is-item-complete {
        text-decoration: line-through;
    }

    .del-single-todo-item {
        background: #ff0000;
        color: #fff;
        padding: 5px 12px;
        cursor: pointer;
        border-radius: 50%;


        &:hover{
            background: #41B883;
            color: #ff0000;

        }

    }
</style>


