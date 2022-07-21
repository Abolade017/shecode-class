<template>
  <div class="max-w">
    <form action="" class="">
      <label for="firstname" class="form-label">Firstname</label>
      <input type="text" class="form-control" v-model="firstname" />
      <label for="lastname" class="form-label">Lastname</label>
      <input type="text" class="form-control" v-model="lastname" />
      <label for="age" class="form-label">Age</label>
      <input type="text" v-model.number="age" class="form-control" />
      <label for="title" class="form-label"> Title</label>
      <div class="form-check" v-for="check in checks" :key="check">
        <input type="checkbox" class="form-check-input" v-model="toggle">
        <label :for="check.value" class="form-check-label">{{check.text}}</label>
      </div>
      <select
        name="title"
        id="title"
        class="form-select"
        v-model="selected"
      >
        <option
          v-for="title in titles"
          :key="title.id"
          :value="title.value"
          class="text-capitalize"
        >
          {{ title.text }}
        </option>
      </select>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      firstname: "",
      lastname: "",
      age: "",
      selected:'Mr',
      toggle:'false',
      titles: [
        {
          id: 1,
          text: "miss",
          value:'Miss'
        },
        {
          id: 2,
          text: "mrs",
           value:'Mrs'
        },
        {
          id: 3,
          text: "mr",
           value:'Mr'
        },
      ],
      checks:[
        {text:'option1', value:'A'},
        {text:'option2', value:'B'},
        {text:'option3', value:'C'}
      ]
    };
  },
};
</script>
<style scoped>
.max-w {
  max-width: 500px;
  margin: 200px auto;
}
</style>
