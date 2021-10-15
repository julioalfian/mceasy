<template>
	<div class="header flex justify-between items-center flex-wrap">
		<div class="haeder_left ">
			<div class="menu_left_title flex items-center">
				<div class="menu_mobile mr-4" @click="handlenav">
					<Menu/>
				</div>
				<h2 class="title text-white">{{title}}</h2>
			</div>
			<p class="text-white opacity-50">{{subTitle}}</p>
		</div>
		<div class="header_right flex items-center">
			<div class="notice">
				<Notice/>
				<span class="active"></span>
			</div>
			<div class="profile flex flex-end items-center ml-6">
				<div class="images mr-3">
					<img alt="" src="../assets/images/profile.jpg" />
				</div>
				<div class="name mr-2 text-white">Nabila</div>
				<ArrowDown/>
			</div>
		</div>
	</div>
</template>

<script>
import Notice from 'vue-material-design-icons/BellOutline.vue';
import ArrowDown from 'vue-material-design-icons/ChevronDown.vue';
import Menu from 'vue-material-design-icons/Menu.vue';
export default {
	props:['title', 'subTitle'],
	components:{
		Notice,
		ArrowDown,
		Menu
	},
	methods:{
		handlenav(){
			console.log('Hii')
			const nav =  document.getElementsByClassName("navigation");
			for(let item of nav){
				item.classList.add("active");
			}
		}
	}
}
</script>
<style lang="scss" scoped>
.menu_mobile{
	display: none;
	@media (max-width: 768px) {
		display: block;
	}
}
.profile{
	cursor: pointer;
	.images{
		width: 42px;
		height: 42px;
		border-radius: 50%;
		overflow: hidden;
		img{
			width: 100%;
			height: 100%;
			object-fit: cover;
		}
	}
	
}
.material-design-icon{
	svg{
		path{
			color: white;
		}
	}
}
.notice{
	position: relative;
	cursor: pointer;
	span.active{
		width: 8px;
		height: 8px;
		border-radius: 50%;
		border: 2px solid #512DA8;
		position: absolute;
		background: #F44336;
		top: 4px;
		right: 4px;
		z-index: 2;
	}
}
</style>