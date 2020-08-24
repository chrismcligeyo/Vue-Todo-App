<template>
    <div id="app">
        <div class="container">
            <Header></Header>
            <img alt="Vue logo" class="logo" src="./assets/logo.png">
            <TodosList :todos="todos"></TodosList>
        </div>

    </div>
</template>

<script>
    import Header from "./components/Header";
    import TodosList from "./components/TodosList";


    export default {
        name: 'App',

        data() {
          return{
            todos: [
              {
                id: 1,
                title: 'Walk the dog',
                completed: true
              },
              {
                id: 2,
                title: 'Go for a Run',
                completed: false
              },
              {
                id: 3,
                title: 'Start Programming Vue To Do App',
                completed: false
              }
            ]
          }

        },
      components: {
        Header,
        TodosList,
      },

      methods: {

      },


    }
</script>

<style lang="scss">
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {

    }

    .container {
        max-width: 800px;
        margin: 0 auto;
    }

    .btn {
        display: inline-block;
        background: #41B883;
        color: #fff;
        padding: 5px;
        border-radius: 5px;
        border: none;
        cursor: pointer;

        &:hover{
            background: #354A21;
            color: #fff;
        }
    }

    .logo {
        display: block;
        margin: 0 auto;
        width: 10%;

    }
</style>
