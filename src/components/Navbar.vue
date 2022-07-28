<template>
  <div class="container-fluid">
    <nav class="navbar navbar-expand-sm justify-content-between">
      <div class="d">
        <img src="@/assets/images/original_logo.png" alt="logo" class="logo" />
      </div>
      <div class="form-group">
        <form action="" class="relative">
          <input type="text" v-model.trim="searchText" class="form-control" />
          <button
            type="button"
            @click="search"
            class="btn btn-warning text-info"
          >
            Submit
          </button>
        </form>
      </div>
      <ul class="navbar-nav justify-content-between">
        <li class="nav-item" v-for="link in links" :key="link.id">
          <router-link
            :to="'/' + link.path"
            class="nav-link text-capitalize"
            :class="{ active: link.linkSelected }"
            @click="selectedLink(link.attr)"
            >{{ link.name }}</router-link
          >
        </li>
      </ul>
    </nav>
    <div class="d-flex p-2 bg-warning">
      <button class="btn" @click="decrement">-</button>
      <button class="btn" @click="increment">+</button>
    </div>
    <p>{{ counter }}</p>
  </div>
</template>
<script>
export default {
  name: "Home",
  data() {
    return {
      links: [
        { id: 1, linkSelected: false, name: "home", attr: "home", path: "" },
        {
          id: 2,
          linkSelected: false,
          name: "about",
          attr: "about",
          path: "about",
        },
        {
          id: 3,
          linkSelected: false,
          name: "contact",
          attr: "contact",
          path: "contact",
        },
        {
          id: 4,
          linkSelected: false,
          name: "our services",
          attr: "service",
          path: "service",
        },
      ],
      searchText: "",
      counter: 0,
    };
  },
  beforeCreated() {
    console.log(this.link);
  },
  create() {
    console.log(this.counter);
  },
  watch: {
    counter(newValue, oldValue) {
      alert(
        `counter has been changed the new value is ${newValue} and the old value is ${oldValue}`
      );
    },
  },
  methods: {
    selectedLink(link) {
      if (link === this.links[0].attr) {
        this.links[0].linkSelected = !this.links[0].linkSelected;
        console.log(this.links[0].linkSelected);
      } else if (link === this.links[1].attr) {
        this.links[1].linkSelected = !this.links[1].linkSelected;
        console.log(this.links[1].linkSelected);
      } else if (link === this.links[2].attr) {
        this.links[2].linkSelected = !this.links[2].linkSelected;
        console.log(this.links[2].linkSelected);
      } else if (link === this.links[3].attr) {
        this.links[3].linkSelected = !this.links[3].linkSelected;
        console.log(this.links[3].linkSelected);
      }
    },
    search() {
      alert(this.searchText);
    },
    increment() {
      return this.counter++;
    },
    decrement() {
      return this.counter--;
    },
  },
};
</script>
<style scoped>
.logo {
  justify-content: space-between;
  align-items: center;
  width: 6rem;
  height: 6rem;
}
.nav-link {
  padding: 0 5rem;
  text-decoration: none;
  color: rgb(198, 136, 20);
  font-weight: 500;
  font-size: large;
}
.active {
  color: white;
  border: solid 1px rgb(198, 136, 20);
  opacity: 0.8;
  background-color: rgb(198, 136, 20);
}
.btn-warning {
  position: absolute;
  right: 0px;
  bottom: 0px;
}
.relative {
  position: relative;
  width: 30rem;
}
:focus.relative {
  outline-color: rgb(198, 136, 20);
}
</style>
