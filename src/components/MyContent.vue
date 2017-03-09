<template>
    <div class="myClase">
        <h2>{{msg}} (<label>{{dynamicScopedProp}}</label>)</h2>
        <label class="form-label">
            Desc 1
            <input v-model="desc1" class="form-control" :disabled="disableEdit">
        </label>
        <br/>
        <label class="form-label">
            Desc 2
            <input v-model="desc2" class="form-control" :disabled="disableEdit">
        </label>
    </div>
</template>

<script>
  export default {
    // Options / Data
    data () { return {
      desc1: 'Esta es una descripción UNO',
      desc2: 'Esta es la descripción DOS'
    } },
    props: {
        'msg': {
        type: String,
        required: true,
        default: ''
      },
      'disableEdit': {default: false}
    },
    // propsData: {},
    computed: {
       dynamicScopedProp: function() {
         return this.msg.length;
       }
     },
    // methods: {},
     watch: {
       desc1 : function(newV, oldV) {
         console.log(oldV + ' -> '+ newV);
       }
     },
    // Options / DOM
    // el () {},
    // template: '',
    // render () {},
    // Options / Lifecycle Hooks
    // beforeCreate () {},
    // created () {},
    // beforeMount () {},
    // mounted () {},
    // beforeUpdate () {},
    // updated () {},
    // activated () {},
    // deactivated () {},
    // beforeDestroy () {},
    // destroyed () {},
    // Options / Assets
    // directives: {},
    // filters: {},
    // components: {},
    // Options / Misc
    // parent: null,
    // mixins: [],
     name: 'my-content'
    // extends: {},
    // delimiters: [ '{{', '}}' ],
    // functional: false
  }
</script>

<style>
.myClase .form-label {
  font-weight: bold;
}
.form-control {
  width: 80%;
}
</style>
