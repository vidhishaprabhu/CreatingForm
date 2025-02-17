<template>
<main>
  <h1>Welcome to my Form</h1>
  <p v-if="age > 18"> You are suitable for vote</p>
  <p v-else-if="age.length == 0">Age should not be blank</p>
  <p v-else>You are not suitable for voting</p>
  <form>
    <div class="mb-3">
      <label for="exampleInputName" class="form-label">Name</label>
      <input type="text" class="form-control" id="exampleInputName" placeholder="Enter Name" v-model="name" value="java">
      <span v-if="nameLength" style="color:red">Name should not be blank</span>
       
    </div>
    <div class="mb-3">
      <label for="exampleInputAge" class="form-label">Age</label>
      <input type="number" class="form-control" id="exampleInputAge" placeholder="Enter your Age" v-model="age">
      <span v-if="ageLength" style="color:red">Age should not be blank</span>
    </div>
    <div class="mb-3">
      <label for="exampleInputEmail" class="form-label">Email</label>
      <input type="email" class="form-control" id="exampleInputEmail" placeholder="Enter Email" v-model="email">
      <span v-if="emailLength" style="color:red">Email should not be blank</span>
    </div>
    <div class="mb-3">
      <label for="exampleInputAddress" class="form-label">Address</label>
      <input type="text" class="form-control" id="exampleInputAddress" placeholder="Enter Address" v-model="address">
      <span v-if="addressLength" style="color:red">Address should not be blank</span>

    </div>
    <label>Skills: </label>
    <br><br>
    <div class="mb-3 form-check">
      <label class="form-check-label" for="java">Java</label>
      <input type="checkbox" class="form-check-input" id="java" value="Java" v-model="technology">

      <br><br>
      <label class="form-check-label" for="html">HTML</label>
      <input type="checkbox" class="form-check-input" id="html" value="HTML" v-model="technology">
      <br><br>
      <label class="form-check-label" for="css">CSS</label>
      <input type="checkbox" class="form-check-input" id="css" value="CSS" v-model="technology">
      <br><br>
      <label class="form-check-label" for="javascript">Javascript</label>
      <input type="checkbox" class="form-check-input" id="javascript" value="Javascript" v-model="technology">
      <br><br>
       <label class="form-check-label" for="vue js">Vue JS</label>
      <input type="checkbox" class="form-check-input" id="vue js" v-model="technology" value="Vue js">
      <br><br>
      <label class="form-check-label" for="bootstrap">Bootstrap</label>
      <input type="checkbox" class="form-check-input" id="bootstrap" v-model="technology" value="Bootstrap">
      <br><br>
      <label class="form-check-label" for="php">PHP</label>
      <input type="checkbox" class="form-check-input" id="php" value="PHP" v-model="technology">
      <br><br>
      <label class="form-check-label" for="sql" value="SQL">SQL</label>
      <input type="checkbox" class="form-check-input" id="sql" value="SQL" v-model="technology">
    </div>
    <label>Type </label>
    <br><br>
    <div class="mb-3 form-check">
      <label class="form-radio-label" for="student">Student</label>
      <input type="radio" class="form-check-input" id="student" value="Student" v-model="type">
      <br><br>
      <label class="form-radio-label" for="employee">Employee</label>
      <input type="radio" class="form-check-input" id="employee" value="Employee" v-model="type">
      <br><br>
      <label class="form-check-label" for="intern">Intern</label>
      <input type="radio" class="form-check-input" id="intern" value="Intern" v-model="type">
      <br><br>
  
    </div>
    <div class="text-center">
      <button type="submit" class="btn btn-primary" v-on:click="getData()">Submit</button>
    </div>

    <p>Name: {{name}}</p>
    <p>Age: {{age}}</p>
    <p>Email: {{email}}</p>
    <p>Address: {{address}}</p>
    <p>Technology: {{technology}}</p>
    <p>I am a: {{type}}</p>
  </form>
</main>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      name: "",
      age:"",
      email: "",
      address: "",
      technology:[],
      type:[],
    }
   

  },
  methods: {
    getData() {
      alert("Name is " + this.name +" and age is "+this.age+" and email is " + this.email + " and address is " + this.address+" and skills are "+this.technology+" and i am a "+this.type);
    }
  },
  computed:{
    nameLength(){
      return this.name.length === 0

    },
    ageLength(){
      return this.age.length === 0
    },
    emailLength(){
      return this.email.length === 0
    },
    addressLength(){
      return this.address.length === 0
    },
    skillsLength(){
      return this.skills.length === 0
    }
  }
}
</script>

<style scoped>
h1 {
  text-align: center;
  color: rgb(101, 125, 105)
}

p {
  color: rgb(115, 155, 215)
}
</style>
