<template>
    <div>

        <div  class="single-todo-item">
<!--            <div>-->
                <div class="single-todo-item-left">
<!--                    <input class="" @change="markComplete" type="checkbox">-->
                    <!--can use above or below. below puts line through on item when checkbox clicked-->
                    <input v-model="todo.completed" type="checkbox">
                    <div v-if="!todo.editing
" @dblclick="editTodo" class="single-todo-item-label" :class="{'is-item-complete':todo.completed}"><!--edit input below will show when you double-click-->
<!--                        <input class="" @change="markComplete" type="checkbox">-->
                        {{todo.title}}
                   </div> <!-- if true, that is !todo.editing show input and title(div with class label) else  if false show input beow. input with v mdel below.   In short its true, so will show div with title and checkbox-->
                    <input v-else type="text" class="single-todo-item-edit" v-model="todo.title"> <!-- if not true, that is if false(todo.editing) show this input-->
                </div>

<!--            </div>-->


            <div @click="removeTodo" class="del-single-todo-item">
                <p class="del-single-todo-item-x">&times;</p> <!-- x symbol html entity-->
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
        methods: {
            // markComplete() {
            //     this.todo.completed = !this.todo.completed;
            // },
            removeTodo() {
                this.$emit('del-todo', this.todo.id)

            },
            editTodo(){
                //to edit todo,means to display edit input first with the todo.title. so when input dblclicked turn editing property to true
                this.$emit('edit-todo',this.todo.id)

            }

        }

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
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
        padding: 5px 5px;
        cursor: pointer;
        border-radius: 50%;

        &:hover {
            background: #41B883;
            color: #ff0000;

        }

        .del-single-todo-item-x{
            padding:15px;
        }

    }
    /*.del-single-todo-item-x{*/
    /*    padding:15px;*/
    /*}*/
    .single-todo-item-left{
        display: flex;
        align-items: center;
      }

    .single-todo-item-label{
        padding: 10px;
        border:1px solid #fff;
        margin-left: 12px;

    }

    .single-todo-item-edit{
        font-size: 20px;
        color:#2c3e50;
        margin-left: 12px;
        width: 100%;
        padding:10px;
        border: 1px solid #ccc;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;

        &:focus{
            outline: none;
        }

    }
</style>


