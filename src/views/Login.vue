<template>
  <div class="login_page">
		<img src="../assets/bg.jpg" alt="" class="bg">
		<div class="bg_grad"></div>
		<Logins/>
  </div>
</template>

<script>
import Logins from "@/components/Login.vue";

export default {
	name: "Login",
	components: {
		Logins,
	},
};

</script>
<style lang="scss" scoped>
.login_page{
	background: #512DA8;
	width: 100%;
	height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
	.bg{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0;
		top: 0;
		object-fit: cover;
		z-index: 0;
	}
	.bg_grad{	
		width: 100%;
		height: 100%;
		background: rgb(0,0,0);
		background: linear-gradient(357deg, rgba(0,0,0,1) 0%, rgba(81,45,168,1) 100%);
		z-index: 1;
		position: absolute;
		left: 0;
		top: 0;
		opacity: .8;
	}
}
</style>
