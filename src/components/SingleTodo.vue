<template>
    <div>
        <div class="single_to-item">
            {{todo.title}}
        </div>

    </div>
</template>

<script>
    export default {
        name: 'SingleTodo',
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
        props: ["todo"],
        components: {},
        methods: {}

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .single-todo-item {
        background: #f4f4f4;
        padding: 5px;
        border-bottom: dotted 1px #cccccc;
    }

    .is-item-complete {
        text-decoration: line-through;
    }

    .del-single-todo-item {
        background: #ff0000;
        color: #fff;
        padding: 5px 12px;
        cursor: pointer;

    }
</style>


