<template>
  <div class="table-responsive push">
    <input type="text" placeholder="Search Doctor" v-model="search"/> 
    <table class="js-table-sections table table-bordered remove-margin-b">
    <thead>
        <tr>
            <th style="width: 60px;"></th>
            <th>Doctor</th>
            <th>Patient</th>
            <th>Product</th>
            <th>status</th>
        </tr>
    </thead>
    <tbody>
         <tr v-for="(d,i) in valueJson">
            <td class="text-center">
                {{Number(i)+1}}
            </td>
            <td>{{d.doctor.name}}</td>
            <td>{{d.patient.name}}</td>
            <td>{{d.product.name}}</td>
            <td>{{d.status.label}}</td>
        </tr>
    </tbody>
    </table>
  </div>
</template>

<script>
import {data} from '../../order-structure.json'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
      return {
          search:'',
          valueJson:{...data}
      }
  },
  watch:{
      search: function(val){
          if(val==""){
              this.valueJson = {...data}
          }else{
              this.valueJson = {...data.filter(e=>{
                  return (e.doctor.name.toLowerCase()).indexOf(val.toLowerCase()) !== -1
              })}
          }
      }
  },
  methods:{
      search(){
        this.valueJson = data
      }
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
