<template>
  <div class="list">
    <div v-for="(item, index ) in this.items" :key="index">
      <span class="badge badge-danger delete" @click="remove(index)">x</span>
      <label>
          <input type="checkbox" name="">
          <i></i>
          <span>
            {{item.title}} - {{item.time}}h - {{item.level}}
          </span>
      </label>
    </div>
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
.list{
    span{
      position: relative;
      left: 40px;
      transition: 0.5s;
      &.badge {
        position: relative;
        left: -8px;
        top: 34px;
        &.badge-danger{
          &.delete{
            cursor: pointer;
          }
        }
      }

    &::before
      {
          content: '';
          position: absolute;
          top: 50%;
          left: 0;
          width: 100%;
          height: 1px;
          background: #fff;
          transform: translateY(-50%) scaleX(0);
          transform-origin: right;
          transition: transform 0.5s;
      }

  }

  h2{
    position: relative;
    display:block;
    margin: 0 0;
    color: #fff;
    font-size: 24px;
    cursor: pointer;
  }

  label {
    position: relative;
    display:block;
    margin: 5px 20px;
    color: #fff;
    font-size: 24px;
    cursor: pointer;
  }

  & input[type="checkbox"]{
    -webkit-appearance: none;
  }

  & i {
    position: absolute;
    top: 6px;
    display: inline-block;
    width: 25px;
    height: 25px;
    border: 2px solid #fff;
  }

  & input[type="checkbox"]:checked ~ i {
      top: 1px;
      border-top: none;
      border-right: none;
      height: 15px;
      width: 25px;
      transform: rotate(-45deg);
  }

  & input[type="checkbox"]:checked ~ span::before {
      transform: translateY(-50%) scaleX(1);
      transform-origin: left;
      transition: transform 0.5s;
  }

  & input[type="checkbox"]:checked ~ span {
    color: #154e6b;
  }

}

</style>
