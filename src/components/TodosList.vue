<template>
    <div class="">
        <div v-for="todo in todos" :key="todo.id">
            <SingleTodo :todo="todo"></SingleTodo>

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
        }

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>


