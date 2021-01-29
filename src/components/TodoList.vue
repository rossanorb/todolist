<template>
  <div>
    <div class="row todolist">
      <div class="col col-md-6 offset-md-3 text-center">
        <h2 class="title">TodoList</h2>
      </div>
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

<style lang="scss" scoped>
.todolist{
  & > div{
    padding: 30px 75px 10px 30px;
    border-top: 50px solid #03a9f4;
  }

  & h2{
    color: #fff;
    font-size: 30px;
    padding: 10px 0;
    margin-left: 10px;
    display: inline-block;
    border-bottom: 4px solid #fff;
  }

}

</style>
