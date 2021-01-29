<template>
  <div class="table-responsive">
    <table  class="table table-hover">
      <thead class="thead-dark">
        <tr>
          <th>Título</th>
          <th>Tempo Estimado</th>
          <th>Nível</th>
          <th>Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index ) in this.items" :key="index">
          <td>
            <div class="form-check">
              <input class="form-check-input" type="checkbox" />
              <label class="form-check-label">
                  {{item.title}}
              </label>
            </div>
          </td>
          <td>{{item.time}}</td>
          <td>
            <span v-bind:class="{
              'badge badge-success': item.level == 'Fácil',
              'badge badge-warning': item.level == 'Médio',
              'badge badge-danger': item.level == 'Difícil'
              }">{{item.level}}</span>
          </td>
          <td><span class="badge badge-danger delete" @click="remove(index)">x</span></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: 'List',
  props: {
    items: Array
  },

  methods: {
    remove: function (id) {
      console.log(id)
      this.$parent.items.splice(id, 1)
    }
  }
}
</script>

<style lang="scss" scoped>
span{
    &.badge {
        &.badge-danger{
            &.delete{
             cursor: pointer;
            }
        }
    }
}
</style>
