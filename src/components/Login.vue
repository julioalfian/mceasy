<template>
  <div class="login_container">
    <div class="logo mb-10">
      <img alt="" src="../assets/logo_mc.webp" />
    </div>
    <div class="form">
      <input
        class="mb-4"
        type="email"
        placeholder="Email"
        v-model="user.email"
      />
      <input type="password" placeholder="Password" v-model="user.password" />
      <button class="btn btn-full-red mt-4" @click.prevent="handleSubmit()">
        Login
      </button>
      <a class="text-center mt-6" href="/">Forgot Password?</a>
      
    </div>
  </div>
</template>

<script>

export default {
  name: "Login",
  data() {
    return {
      user: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    handleSubmit() {
			
      if (
        this.user.email == "test@test.com" &&
        this.user.password == "test@test.com"
      ) {
        this.$router.push("/customers")
				//localStorage.setItem('user', this.user)
      } else {
        alert("email dan password anda salah");
      }
    },
  },
};
</script>

<style lang="scss" scoped>

.login_container {
  width: 440px;
  height: auto;
  background: white;
  border-radius: 10px;
  padding: 3rem 2rem;
  display: block;
  z-index: 2;

  background: rgba( 255, 255, 255, 0.35 );
  box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.40 );
  backdrop-filter: blur( 3.5px );
  -webkit-backdrop-filter: blur( 3.5px );
  border-radius: 10px;
  border: 1px solid rgba( 255, 255, 255, 0.18 );


  .logo {
    text-align: center;
    img {
      width: 120px;
      margin: 0 auto;
    }
  }
}
</style>
