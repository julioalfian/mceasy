<template>
  <div class="home_page flex">
    <Nav/>
    <AddCustomer/>
  </div>
</template>

<script>

import Nav from "@/components/Navigation.vue";
import AddCustomer from "@/components/AddCustomer.vue";

export default {
  name: "AddCustomers",
  components: {
    Nav,
    AddCustomer
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
