<template>
  <div class="max-w">
    <form action="" class="" @submit.prevent="submitForm">
      <label for="firstname" class="form-label">Firstname</label>
      <input type="text" class="form-control" v-model="firstname" />
      <label for="lastname" class="form-label">Lastname</label>
      <input type="text" class="form-control" v-model="lastname" />
      <label for="age" class="form-label">Age</label>
      <input type="text" v-model.number="age" class="form-control" />

      <label for="email" class="form-label"> Email</label>
      <input
        type="email"
        v-model.trim="email"
        class="form-control"
        @blur="validateEmail"
        :class="{
          invalidEmail: validityMessage === 'please enter Valid email',
        }"
      />
      <p v-if="validateEmail">{{ validityMessage }}</p>
      <div class="form-check" v-for="check in checks" :key="check">
        <input type="checkbox" class="form-check-input" v-model="toggle" />
        <label :for="check.value" class="form-check-label">{{
          check.text
        }}</label>
      </div>
      <select name="title" id="title" class="form-select" v-model="selected">
        <option
          v-for="title in titles"
          :key="title.id"
          :value="title.value"
          class="text-capitalize"
        >
          {{ title.text }}
        </option>
      </select>
      <button class="btn btn-warning" type="submit" @click="submitForm">
        submit
      </button>
    </form>
    <button type="button" class="btn btn-lg btn-primary" @click="increment">
      increase
    </button>
    <button type="button" class="btn btn-lg btn-primary" @click="decrement">
      decrease
    </button>

    <p>{{ counter }}</p>
    <p>{{ fullname }}</p>
  </div>
</template>
<style scoped>
.invalidEmail {
  border-color: red;
}
</style>
<script>
export default {
  data() {
    return {
      firstname: "",
      lastname: "",
      age: "",
      email: "",
      selected: "Mr",
      toggle: "false",
      message: "",
      validityMessage: "",
      titles: [
        {
          id: 1,
          text: "miss",
          value: "Miss",
        },
        {
          id: 2,
          text: "mrs",
          value: "Mrs",
        },
        {
          id: 3,
          text: "mr",
          value: "Mr",
        },
      ],
      checks: [
        { text: "option1", value: "A" },
        { text: "option2", value: "B" },
        { text: "option3", value: "C" },
      ],
      counter: 0,
    };
  },
  watch:{
    submit(newValue, oldValue){
      setTimeout()
    }
  },
  methods: {
    increment() {
      return this.counter++;
    },
    decrement() {
      return this.counter--;
    },
    validateEmail() {
      if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email)) {
        this.validityMessage = "valid";
      } else {
        this.validityMessage = "please enter Valid email";
      }
    },
    submitForm() {
      if (this.firstname === "" || this.lastname === "" || this.email === ""||this.age==="") {
        alert("please enter the empty field");
      } else {
        alert("Input Succesful");
      }
    },
  },
  computed: {
    fullname() {
      return this.firstname + " " + this.lastname;
    },
  },
};
</script>
<style scoped>
.max-w {
  max-width: 500px;
  margin: 200px auto;
}
</style>
