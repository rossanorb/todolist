<template>
  <div class="container">
    <TodoList />
  </div>
</template>

<script>
// @ is an alias to /src
import TodoList from '@/components/TodoList'

export default {
  name: 'Home',
  components: {
    TodoList
  }
}
</script>
