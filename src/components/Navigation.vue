<template>
  <div class="navigation">
		<div class="navigation_container">
			<div class="close_mobile" @click="handlenav">
				<Close/>
			</div>
			<div class="nav_logo">
				<img alt="" src="../assets/logo_mc.webp" />
			</div>
			<div class="navigation_menu">
				<router-link to="/home">
					<div class="nav_items flex">
						<Home />
						<div class="text">Dashboard</div>
					</div>
				</router-link>
				<div class="nav_label uppercase mt-4 mb-2">Main Menu</div>
				<router-link to="/analytics">
					<div class="nav_items flex">
						<Chart />
						<div class="text">Analytics</div>
					</div>
				</router-link>
				<router-link to="/customers">
					<div class="nav_items flex">
						<User />
						<div class="text">Customers</div>
					</div>
				</router-link>
				<router-link to="/products">
					<div class="nav_items flex">
						<Tag />
						<div class="text">Products</div>
					</div>
				</router-link>
				<router-link to="/orders">
					<div class="nav_items flex">
						<Cart />
						<div class="text">Orders</div>
					</div>
				</router-link>
				<router-link to="/reports">
					<div class="nav_items flex">
						<Report />
						<div class="text">Reports</div>
					</div>
				</router-link>

				<div class="nav_label uppercase mt-4 mb-2">Help</div>
				<router-link to="/settings">
					<div class="nav_items flex">
						<Setting />
						<div class="text">Settings</div>
					</div>
				</router-link>
				<router-link to="/support">
					<div class="nav_items flex">
						<Support />
						<div class="text">Support</div>
					</div>
				</router-link>
				
			</div>
		</div>
	</div>
</template>
<script>
//import MenuIcon from 'vue-material-design-icons/Menu.vue';
import Home from 'vue-material-design-icons/Home.vue';
import Chart from 'vue-material-design-icons/ChartLine.vue';
import User from 'vue-material-design-icons/AccountGroup.vue';
import Tag from 'vue-material-design-icons/Tag.vue';
import Cart from 'vue-material-design-icons/CartOutline.vue';
import Report from 'vue-material-design-icons/ChartBoxOutline.vue';
import Setting from 'vue-material-design-icons/CogOutline.vue';
import Support from 'vue-material-design-icons/FaceAgent.vue';
import Close from 'vue-material-design-icons/Close.vue';


export default {
	components: {
		//MenuIcon,
		Home,
		Chart,
		User,
		Tag,
		Cart,
		Report,
		Setting,
		Support,
		Close
	},
	methods:{
		handlenav(){
			const nav =  document.getElementsByClassName("navigation");
			for(let item of nav){
				item.classList.remove("active");
			}
		}
	}
}
</script>

<style lang="scss" scoped>
.close_mobile{
	display: none;
	@media (max-width: 768px) {
		display: block;
		position: absolute;
		right: 16px;
		top: 16px;
	}
}
.navigation{
	width: 250px;
	min-height: 100vh;
	background: rgb(255, 255, 255);
	padding: 2rem;
	transition: .3s;
	@media (max-width: 768px) {
		position: absolute;
		left: -250px;
		top: 0;
		height: 100%;
		z-index: 10;
		&.active{
			left: 0;
		}
	}
	.nav_logo{
		margin-bottom: 50px;
		img{
			margin: 0 auto;
			width: 120px;
		}
	}
}
.nav_label{
	font-size: 10px;
	color: #BDBDBD;
}
.nav_items{
	margin-bottom: 1rem;
	.text{
		font-size: 16px;
		color: #BDBDBD;
		margin-left: 8px;
		transition: .3s;
	}
	svg{
		width: 16px;
		path{
			color: #BDBDBD;
			transition: .3s;
		}
	}
	&:hover{
		.text{
			color: #F44336;
		}
		svg{
			path{
				color: #F44336;
			}
		}
	}
}
.router-link-exact-active {
  .nav_items{
		position: relative;
		&::after{
			content: '';
			width: 4px;
			height: 100%;
			position: absolute;
			left: -16px;
			top: 0;
			background: #F44336;
			z-index: 2;
		}
		.text{
			color: #F44336;
		}
		svg{
			path{
				color: #F44336;
			}
		}
	}

}

</style>