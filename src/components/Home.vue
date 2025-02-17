<template>
<main>
  <h1>Welcome to my Form</h1>
  <p v-if="age > 18"> You are suitable for vote</p>
  <p v-else-if="age.length == 0"></p>
  <p v-else>You are not suitable for voting</p>
  <form>
    <div class="mb-3">
      <label for="exampleInputName" class="form-label mainlabel">Name</label>
      <input type="text" class="form-control" id="exampleInputName" placeholder="Enter Name" v-model="name" value="java" ref="inputName" @keydown.enter="handleKeyPress($event, 'inputAge')">
      <span v-if="nameLength" style="color:red">Name should not be blank</span>

    </div>
    <div class="mb-3">
      <label for="exampleInputAge" class="form-label mainlabel">Age</label>
      <input type="number" class="form-control" id="exampleInputAge" placeholder="Enter your Age" v-model="age" ref="inputAge" @keydown.enter="handleKeyPress($event,'inputEmail')">
      <span v-if="ageLength" style="color:red">Age should not be blank</span>
    </div>
    <div class="mb-3">
      <label for="exampleInputEmail" class="form-label mainlabel">Email</label>
      <input type="email" class="form-control" id="exampleInputEmail" placeholder="Enter Email" v-model="email" ref="inputEmail" @keydown="handleKeyPress($event,'inputAddress')">
      <span v-if="emailLength" style="color:red">Email should not be blank</span>
    </div>
    <div class="mb-3">
      <label for="exampleInputAddress" class="form-label mainlabel">Address</label>
      <input type="text" class="form-control" id="exampleInputAddress" placeholder="Enter Address" v-model="address" ref="inputAddress" @keydown="(handleKeyPress($event,'javaCheckbox'))">
      <span v-if="addressLength" style="color:red">Address should not be blank</span>

    </div>
    <label class="mainlabel">Skills </label>
    <br><br>
    <div class="mb-3 form-check">
      <label class="form-check-label" for="java">Java</label>
      <input type="checkbox" class="form-check-input" id="java" value="Java" v-model="technology" ref="javaCheckbox" @keydown="(handleKeyPress($event,'htmlCheckbox'))">

      <br><br>
      <label class="form-check-label" for="html">HTML</label>
      <input type="checkbox" class="form-check-input" id="html" value="HTML" v-model="technology" ref="htmlCheckbox" @keydown="(handleKeyPress($event,'cssCheckbox'))">
      <br><br>
      <label class="form-check-label" for="css">CSS</label>
      <input type="checkbox" class="form-check-input" id="css" value="CSS" v-model="technology" ref="cssCheckbox" @keydown="(handleKeyPress($event,'javascriptCheckbox'))">
      <br><br>
      <label class="form-check-label" for="javascript">Javascript</label>
      <input type="checkbox" class="form-check-input" id="javascript" value="Javascript" v-model="technology" ref="javascriptCheckbox" @keydown="(handleKeyPress($event,'vuejsCheckbox'))">
      <br><br>
      <label class="form-check-label" for="vue js">Vue JS</label>
      <input type="checkbox" class="form-check-input" id="vue js" v-model="technology" value="Vue js" ref="vuejsCheckbox" @keydown="(handleKeyPress($event,'bootstrapCheckbox'))">
      <br><br>
      <label class="form-check-label" for="bootstrap">Bootstrap</label>
      <input type="checkbox" class="form-check-input" id="bootstrap" v-model="technology" value="Bootstrap" ref="bootstrapCheckbox" @keydown="(handleKeyPress($event,'phpCheckbox'))">
      <br><br>
      <label class="form-check-label" for="php">PHP</label>
      <input type="checkbox" class="form-check-input" id="php" value="PHP" v-model="technology" ref="phpCheckbox" @keydown="(handleKeyPress($event,'sqlCheckbox'))">
      <br><br>
      <label class="form-check-label" for="sql" value="SQL">SQL</label>
      <input type="checkbox" class="form-check-input" id="sql" value="SQL" v-model="technology" ref="sqlCheckbox" @keydown="(handleKeyPress($event,'studentRadio'))">
    </div>
    <label class="mainlabel">Type </label>
    <br><br>
    <div class="mb-3 form-check">
      <label class="form-radio-label" for="student">Student</label>
      <input type="radio" class="form-check-input" id="student" value="Student" v-model="type" ref="studentRadio" @keydown="(handleKeyPress($event,'employeeRadio'))">
      <br><br>
      <label class="form-radio-label" for="employee">Employee</label>
      <input type="radio" class="form-check-input" id="employee" value="Employee" v-model="type" ref="employeeRadio" @keydown="(handleKeyPress($event,'internRadio'))">
      <br><br>
      <label class="form-check-label" for="intern">Intern</label>
      <input type="radio" class="form-check-input" id="intern" value="Intern" v-model="type" ref="internRadio" @keydown="(handleKeyPress($event,'submitbtn'))">
      <br><br>

    </div>
    <div class="text-center">
      <button type="submit" class="btn btn-primary" v-on:click="getData()" refs="submitbtn" ref="submitbtn" id="button">Submit</button>
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
      age: "",
      email: "",
      address: "",
      technology: [],
      type: [],
    }

  },

  methods: {
    handleKeyPress(event, nextField) {
      if (event.key === "Enter") {
        event.preventDefault();
        if (nextField) {
          this.$refs[nextField].focus();
        }
      }
    },
    getData() {
      if (!this.name) {
        this.$refs.inputName.focus();
        return;
      }
      if (!this.age) {
        this.$refs.inputAge.focus();
        return;
      }
      if (!this.email) {
        this.$refs.inputEmail.focus();
        return;
      }
      if (!this.address) {
        this.$refs.inputAddress.focus();
        return;
      }
      if (!this.technology) {
        
        if(htmlCheckbox){
          this.$refs.htmlCheckbox.focus();
        
        }
        if(javaCheckbox)
        {
          this.$refs.javaCheckbox.focus();
        }
        if(htmlCheckbox)
        {
          this.$refs.htmlCheckbox.focus();
        }
        if(cssCheckbox)
        {
          this.$refs.cssCheckbox.focus();
        }
        if(javascriptCheckbox)
        {
          this.$refs.javascriptCheckbox.focus();
        }
        if(vuejstCheckbox)
        {
          this.$refs.vuejsCheckbox.focus();
        }
        if(bootstrapCheckbox)
        {
          this.$refs.bootstrapCheckbox.focus();
        }
        if(phpCheckbox)
        {
          this.$refs.phpCheckbox.focus();
        }
        if(sqlCheckbox)
        {
          this.$refs.sqlCheckbox.focus();
        }

        return;
      }
      if(!this.type){
        if(studentRadio){
          this.$refs.studentRadio.focus();
        }
        else if(employeeRadio){
          this.$refs.employeeRadio.focus();
        }
        else if(internRadio){
          this.$refs.internRadio.focus();
        }
      }
      if(submitbtn){
        this.$refs.submitbtn.focus();
      }

    }
  },
  computed: {
    nameLength() {
      return this.name.length === 0

    },
    ageLength() {
      return this.age.length === 0
    },
    emailLength() {
      return this.email.length === 0
    },
    addressLength() {
      return this.address.length === 0
    },
    skillsLength() {
      return this.skills.length === 0
    },

  }

}
</script>

<style scoped>
main {
  background-color: rgb(209, 207, 38);
  color: black;
}

h1 {
  text-align: center;
  color: rgb(101, 125, 105)
}

p {
  color: rgb(115, 155, 215);
  font-size:15px
}
label{
  font-size:25px
}
#button{
  width:250px
}
.mainlabel{
  color:aliceblue;
  font-weight: 800;
}
</style>
