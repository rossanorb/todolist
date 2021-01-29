<template>
  <div>
    <div class="row">
      <div class="col col-md-6 offset-md-3 text-center"><h2>TodoList</h2></div>
    </div>
    <div class="row">
      <div class="col col-md-6 offset-md-3">
        <Form @add="add" />
      </div>
    </div>
    <div class="row">
      <div class="col col-md-6 offset-md-3">
        <List :items="this.items" />
      </div>
    </div>
  </div>
</template>

<script>
import Form from './Form'
import List from './List'
export default {
  name: 'TodoList',
  components: {
    Form,
    List
  },
  data: function () {
    return {
      items: []
    }
  },

  methods: {
    add: function (task) {
      this.items.push(task)
    }
  }
}
</script>
