<template>
    <form @submit="submit">

        <div class="form-group">
            <label for="uname">Título:</label>
            <input type="text" v-bind:class="{ 'form-control is-invalid': titleIsInvalid, 'form-control': !titleIsInvalid }" id="title" name="title" v-model="title" >
            <div class="valid-feedback">Valid.</div>
            <div class="invalid-feedback">Campo obrigatório.</div>
        </div>

        <div class="form-group">
            <label for="uname">Tempo estimado em horas:</label>
            <input type="text" v-bind:class="{ 'form-control is-invalid': timeIsInvalid, 'form-control': !timeIsInvalid }" id="time" name="time" v-model="time" >
            <div class="valid-feedback">Valid.</div>
            <div class="invalid-feedback">Campo tempo estimado é inválido.Informe um valor e inteiro</div>
        </div>

        <div class="form-group">
            <label for="uname">Nível de dificuldade:</label>
            <select id="level" v-bind:class="{ 'form-control is-invalid': levelIsInvalid, 'form-control': !levelIsInvalid }"  v-model="level">
                <option selected="selected" value="">Selecione...</option>
                <option value="Fácil">Fácil</option>
                <option value="Médio">Médio</option>
                <option value="Difícil">Difícil</option>
            </select>
            <div class="valid-feedback">Valid.</div>
            <div class="invalid-feedback">Uma opção deve ser selecionada</div>
        </div>

        <div class="col-md-12 mt-5">
            <div class="form-group row">
                <button type="submit" class="btn btn-primary ml-1" >Adicionar</button>
            </div>
        </div>

    </form>
</template>

<script>
export default {
  name: 'Form',
  data: function () {
    return {
      title: null,
      time: null,
      level: '',
      titleIsInvalid: false,
      timeIsInvalid: false,
      levelIsInvalid: false
    }
  },

  methods: {
    clear: function () {
      this.titleIsInvalid = false
      this.timeIsInvalid = false
      this.levelIsInvalid = false
    },

    checkForm: function () {
      this.clear()

      if (!this.title) {
        this.titleIsInvalid = true
      }

      if (!Number.isInteger(+this.time) || (+this.time) <= 0) {
        this.timeIsInvalid = true
      } else {
        this.time = +this.time
      }

      if (!this.level) {
        this.levelIsInvalid = true
      }

      if (this.titleIsInvalid || this.timeIsInvalid || this.levelIsInvalid) {
        return false
      }

      return true
    },

    submit: function (e) {
      if (this.checkForm()) {
        this.$emit('add', {
          title: this.title,
          time: this.time,
          level: this.level
        })

        this.title = ''
        this.time = ''
        this.level = ''
      }
      e.preventDefault()
    }

  }
}
</script>
