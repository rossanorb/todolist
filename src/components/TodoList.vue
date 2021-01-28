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
  </div>
</template>

<script>
import Form from './Form'
export default {
  name: 'TodoList',
  components: {
    Form
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
