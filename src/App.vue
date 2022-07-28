<template>
  <!-- <div id="nav"> -->
  <!-- <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
  <!-- </div> -->
  <!-- <div>
    <header>
      <div class="flex align-items-center">
        <input type="radio" v-model="current" value="About" id="" />
        <input type="radio" v-model="current" value="HelloWorld" id="" />
      </div>

      <keepAlive>
        <component :is="current"></component>
      </keepAlive>
    </header> -->
    <router-view />
  <!-- </div> -->
</template>
<script>
import About from "@/components/about.vue";
import HelloWorld from "@/components/HelloWorld.vue";
export default {
  components: {
    HelloWorld,
    About,
  },
  data() {
    return {
      current: "HelloWorld",
    };
  },
};
</script>

<style></style>
