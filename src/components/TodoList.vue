<template>
  <div>
    <div class="row">
      <div class="col col-md-6 offset-md-3">Teste</div>
    </div>
    <div class="row">
      <div class="col col-md-6 offset-md-3">
        <form @submit="submit">
          <div class="form-group">
            <label for="uname">Título:</label>
            <input type="text" class="form-control" id="title" name="title" v-model="title" >
          </div>
          <div class="form-group">
            <label for="uname">Tempo estimado em horas:</label>
            <input type="text" class="form-control" id="time" name="time" v-model="time" >
          </div>
          <div class="form-group">
            <label for="uname">Nível de dificuldade:</label>
            <select id="level" class="form-control" v-model="level">
                <option selected="selected" value="0">Selecione...</option>
                <option value="1">Fácil</option>
                <option value="2">Médio</option>
                <option value="3">Difícil</option>
            </select>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  data: function () {
    return {
      title: null,
      time: null,
      level: null
    }
  },

  methods: {

    checkForm: function (e) {
      e.preventDefault()
    },

    submit: function (e) {
      if (this.checkForm()) {
      }
    }

  }
}
</script>
