<template>
  <div class="home_page flex">
    <Nav/>
    <Customers/>
  </div>
</template>

<script>
// @ is an alias to /src
import Nav from "@/components/Navigation.vue";
import Customers from "@/components/Customers.vue";

export default {
  name: "Home",
  components: {
    Nav,
    Customers
  },
  
};
</script>

<style lang="scss" scoped>
.home_page{
  position: relative;
}
#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
