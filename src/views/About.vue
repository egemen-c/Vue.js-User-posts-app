<template>
  <div id="app">
    <div class="container">
      <table class="table">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Name</th>
            <th scope="col">Nickname</th>
            <th scope="col">Company</th>
            <th scope="col">Address</th>
            <th scope="col">Details</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in users" :key="user.id">
            <th scope="row">{{user.id}}</th>
            <td>{{user.name}}</td>
            <td>@{{user.username}}</td>
            <td>{{user.company.name}}</td>
            <td>{{user.address.city}}</td>
            <td>
              <button class="btn btn-primary btn-md" @click="userDetail(user.id)">User Post<span class="fa fa-edit"></span>
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'App',
    data() {
      return {
        users: []
      }
    },
    methods: {
      userDetail(id) {
        this.$router.push({
          name: 'user',
          params: {
            userId: `${id}`
          }
        })
      },
    },
    created() {
      fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(json => this.users = json)
    },
  }
</script>