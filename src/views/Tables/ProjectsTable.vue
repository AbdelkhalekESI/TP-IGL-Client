<template>
  <div class="card shadow"
       :class="type === 'dark' ? 'bg-default': ''">
    <div class="card-header border-0"
         :class="type === 'dark' ? 'bg-transparent': ''">
      <div class="row align-items-center">
        <div class="col">
          <h3 class="mb-0" :class="type === 'dark' ? 'text-white': ''">
            {{title}}
          </h3>
        </div>
        <!-- <div class="col text-right">
          <base-button type="primary" size="sm">Afficher tout</base-button>
        </div> -->
      </div>
    </div>

    <div class="table-responsive">
      <base-table class="table align-items-center table-flush"
                  :class="type === 'dark' ? 'table-dark': ''"
                  :thead-classes="type === 'dark' ? 'thead-dark': 'thead-light'"
                  tbody-classes="list"
                  :data="tableData">
        <template slot="columns">
          <th>Matricule</th>
          <th>Nom</th>
          <th>Prénom</th>
          <th>Promo</th>
          <th>Groupe</th>
          <th></th>
        </template>

        <template slot-scope="{row}">
          <td class="budget">
            {{row.matricule}}
          </td>
          <td class="budget">
            {{row.first_name}}
          </td>
          <td class="budget">
            {{row.last_name}}
          </td>
         <td class="budget">
            {{row.promo}}
          </td>
         <td class="budget">
            {{row.groupe}}
          </td>

          <td class="text-right">
            <base-dropdown class="dropdown"
                           position="right">
              <a slot="title" class="btn btn-sm btn-icon-only text-light" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                <i class="fas fa-ellipsis-v"></i>
              </a>

              <template>
                <a v-on:click="deleteStudent(row.id)" class="dropdown-item" href="#">Supprimer</a>
              </template>
            </base-dropdown>
          </td>

        </template>

      </base-table>
    </div>

 

  </div>
</template>
<script>
const axios = require('axios').default;

  export default {
    name: 'projects-table',
    props: {
      type: {
        type: String
      },
      title: String
    },
    data() {
      return {
        tableData : []
      }
    },
    methods : {
      deleteStudent : function(id) {
        axios
        .delete('http://127.0.0.1/api/students/' + id)
        .then(res => {
          alert(res.data.message)
          this.getAllStudents() ;
        })
        .catch(err => console.log("Error while Deleting Student" + err))
    } , 
    getAllStudents : function () {
  axios
        .get('http://127.0.0.1/api/students')
        .then(res => {
         this.tableData = res.data.data
         console.log(res.data.data)
        })
        .catch(err => console.log("Error while fetching Data" + err))
    },
      },
    mounted () {
    this.getAllStudents() ;
    }
  }
</script>
<style>
</style>
