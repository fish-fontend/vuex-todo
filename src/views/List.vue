<template>
  <div>
    <Tab></Tab>
    <add-todo></add-todo>
    <hr>
    <todo-list></todo-list>
  </div>
</template>

<script>
// @ is an alias to /src
import AddTodo from '@/components/AddTodo.vue'
import TodoList from '@/components/TodoList.vue'
import Tab from '@/components/Tab.vue'

export default {
  name: 'home',
  components: {
    'add-todo': AddTodo,
    'todo-list': TodoList,
    Tab
  },
  watch: {
    '$store.state.isLogin': function (newLoginState) {
      if (newLoginState === false) {
        this.$router.push('/login')
      }
    }
  }
}
</script>
