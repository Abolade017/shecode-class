<template>
  <div>
    <Navbar />
    <HelloWorld />
  </div>
</template>
<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import HelloWorld from "@/components/HelloWorld.vue";
export default {
  components: { Navbar, HelloWorld },
};
</script>
