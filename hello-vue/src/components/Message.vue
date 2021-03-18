<template>
  <div class="message">
    <h1>{{ tittle }}</h1>
    
    <h3>Data Elements</h3>
    <button @click="addInput"><span>Add</span></button>
    <div class="form-group" v-for="(field,k) in fields" :key="k">
      <span>Data Element #</span>
      <input type="text" class="form-control" v-model="field.number" :key="k"/>
      <span>Data Element value</span>
      <input type="text" class="form-control" v-model="field.value" :key="k"/>
    </div>
    <button type="submit"><span>Send</span></button>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      fields: [{
        number: '',
        value: '',
      }]
    }
  },
  name: 'Message',
  props: {
    msg: String,
    tittle: String,
    
  },
  methods: {
    addInput() {
      this.fields.push({ number: "", value: "" });        
    },
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
