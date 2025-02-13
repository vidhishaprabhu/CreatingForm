<template>
<main>
  <h1>Welcome to my Form</h1>
  <form>
    <div class="mb-3">
      <label for="exampleInputName" class="form-label">Name</label>
      <input type="text" class="form-control" id="exampleInputName" placeholder="Enter Name" v-model="name">
    </div>
    <div class="mb-3">
      <label for="exampleInputEmail" class="form-label">Email</label>
      <input type="email" class="form-control" id="exampleInputEmail" placeholder="Enter Email" v-model="email">
    </div>
    <div class="mb-3">
      <label for="exampleInputAddress" class="form-label">Address</label>
      <input type="text" class="form-control" id="exampleInputAddress" placeholder="Enter Address" v-model="address">

    </div>
    <div class="text-center">
      <button type="submit" class="btn btn-primary" v-on:click="getData()">Submit</button>
    </div>

    <p>Name: {{name}}</p>
    <p>Email: {{email}}</p>
    <p>Address: {{address}}</p>
  </form>
</main>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      name: "",
      email: "",
      address: "",
    }

  },
  methods: {
    getData() {
      alert("Name is " + this.name + " and email is " + this.email + " and address is " + this.address);
    }
  }
}
</script>

<style scoped>
h1 {
  text-align: center;
  color: rgb(101, 125, 105)
}
p{
  color:rgb(115, 155, 215)
}
</style>
