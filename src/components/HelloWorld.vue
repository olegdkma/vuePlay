<template>
  <div class="row">
    <div class="col-9">

      <resulting-form v-bind:options="settings"/>
    </div>
    <div class="col-3">
      <aside-form v-on:formStyleSettings="updateFormSettings"/>
    </div>


  </div>
</template>

<script>
  import resultingForm from "./resultingForm";
  import asideForm from "./asideForm";

export default {
  name: 'HelloWorld',
  components: {asideForm, resultingForm},
  props: {
    msg: String,

  },
  data() {
    return{
      settings: undefined
    }
  },
  methods: {
    updateFormSettings: function (value) {
      this.settings = value

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
  *{
    box-sizing: border-box;
  }
  .col-9{
    width: 75%;
  }
  .col-3{
    width: 25%;
  }
  .row{
    display: flex;
  }
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
