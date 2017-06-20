<template>
  <div id="app">
    <md-card>
      <md-card-header>
        <div class="md-title">
          Material Design with Vue.js 2 
        </div>
        <div class="md-subhead">
          By Andrés Matta Morales
        </div>  
      </md-card-header>
      <md-card-content>
          <md-button class="md-raised md-primary" v-on:click.native="fillTable()">Fill Table</md-button>
          <md-button class="md-raised md-primary" v-on:click.native="clearTable()">Clear Table</md-button>
      </md-card-content>
      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>First Name</md-table-head>
            <md-table-head>Last Name</md-table-head>
            <md-table-head>Email</md-table-head>
          </md-table-row>
        </md-table-header>
        <md-table-body>
          <md-table-row v-for="contact in contacts">
            <md-table-cell>{{ contact.firstName }}</md-table-cell>
            <md-table-cell>{{ contact.lastName }}</md-table-cell>
            <md-table-cell>{{ contact.email }}</md-table-cell>
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: function(){
    return {
      contacts: []
    }
  },
  methods: {
    fillTable: function(){

      this.contacts.push({
        firstName: 'Andrés',
        lastName: 'Matta',
        email: 'amttdev@gmail.com'
      });

      this.contacts.push({
        firstName: 'Esa',
        lastName: 'Loquita',
        email: 'am123@gmail.com'
      });

      this.contacts.push({
        firstName: 'Gerardo',
        lastName: 'Matta',
        email: 'gmttsc@gmail.com'
      });

    },

    clearTable: function(){
      this.contacts.splice(0, this.contacts.length);
    }
  }
}
</script>

<style>
#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right: 30px;
}
</style>
