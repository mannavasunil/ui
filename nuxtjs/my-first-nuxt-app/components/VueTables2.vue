<template>
    <!-- rows, columns and options (I will show how to define them, keep reading) -->
<ClientTable :data="rows" :columns="columns" :options="options"></ClientTable>
</template>


<script>
import {ClientTable, Event} from 'vue-tables-2';
import Vue from 'vue';
Vue.use(ClientTable);
import daterangepicker from 'daterangepicker';
//This is very important to used with the window object
window.moment = require('moment');

export default {
    data(){
            return{
                columns: [ 'id', 'name','birth','year','number'],
                rows:[
      {id:1, name:"John",birth:moment("2004-05-19"), year:"5", number:"17"},
      {id:2, name:"Jane",birth:moment("2004-05-19"), year:"6", number:"18"},
      {id:3, name:"Susan",birth:moment("2004-05-19"), year:"7", number:"19"},
      {id:4, name:"Chris",birth:moment("2004-05-19"), year:"8", number:"20"},
      {id:5, name:"Dan",birth:moment("2004-05-19"), year:"9", number:"21"}
],
                options: {
                    filterByColumn: true,
                    perPage:2,
                    texts: {
                        filter: "Filtrar:",
                        filterBy: 'Filtrar por {column}',
                        count:' '
                    },
                    dateColumns:['birth'],
                    dateFormat: 'YYYY-MM-DD',
                    datepickerOptions: {
                        showDropdowns: true,
                        autoUpdateInput: true,
                    },
                    pagination: { chunk:10,dropdown:false },
                    filterable:['name','birth','year'],
                    headings: {
                        name: 'Student Name',
                        year: 'Year in School',
                        number: 'Number ID',
                        id: 'ID',
                      },
                }
            }
            
        }
}
</script>