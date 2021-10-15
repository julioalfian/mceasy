<template>
	<div class="customers">
		<Header title="Add New Customer" subTitle="Fill the form to add new customers."/>
		<div class="customers_container mt-4 px-5 py-5">
			<div class="breadcrumb mb-4">
				<ol>
					<li>
						Customers
					</li>
					<li class="active">
						Add New Customer
					</li>
				</ol>
			</div>
			<form action="" class="add_customer_form">
				<div class="flex justify-between flex-wrap md:flex-nowrap">
					<div class="left">
						<div class="photo mb-4">
							<img src="" alt="" class="profile">
							<div class="sample">
								<Images/>
								<div class="brose">
									<p>Brose Photo</p>
									<p>(JPEG, JPG, PNG)</p>
								</div>
							</div>
						</div>
						<div class="form-group mb-4">
							<input type="file" id="profile" accept="image/png, image/jpg, image/jpeg">
							<label for="profile">Upload</label>
						</div>
						<div class="btn_remove mb-4">Remove</div>
					</div>
					<div class="center">
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Full name</label>
								<p class="required">*required</p>
							</div>
							<input type="text" placeholder="Enter full name">
						</div>
						<div class="form-group fit-content">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Gender</label>
								<p class="required">*required</p>
							</div>
							<div class="flex">
								<input type="radio" name="gender" id="male">
								<label for="male" class="label_radio ml-2 mr-6">Male</label>
								<input type="radio" name="gender" id="female">
								<label for="female" class="label_radio ml-2">Female</label>
							</div>
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Date of birth</label>
								<p class="required">*required</p>
							</div>
							<input type="date" placeholder="dd/mm/yy">
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Identity Number</label>
								<p class="required">*required</p>
							</div>
							<select name="identity" id="identity" placeholder="KTP/SIM/Other">
								<option value="ktp">KTP</option>
								<option value="sim">SIM</option>
								<option value="stnk">STNK</option>
							</select>
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Identity Number</label>
								<p class="required">*required</p>
							</div>
							<input type="number" placeholder="Enter identity number">
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Email</label>
								<p class="required">*required</p>
							</div>
							<input type="email" placeholder="Enter email">
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Phone Number</label>
								<p class="required">*required</p>
							</div>
							<div class="phone flex">
								<select name="phone_code" id="phone_code">
									<option value="62">+62</option>
									<option value="61">+61</option>
									<option value="60">+60</option>
								</select>
								<input type="number" placeholder="Enter phone number">
							</div>
						</div>

					</div>
					<div class="right">
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Address</label>
								<p class="required">*required</p>
							</div>
							<textarea name="address" id="address" cols="30" rows="3" placeholder="enter address"></textarea>
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">Detail Address</label>
								<p class="required">*required</p>
							</div>
							<textarea name="address" id="address" cols="30" rows="2" placeholder="enter details address: (Stret, block, number, etc)"></textarea>
						</div>
						<div class="form-group">
							<div class="flex justify-between items-center">
								<label for="" class="uppercase">instagram</label>
								
							</div>
							<input type="text" placeholder="Enter instagram">
						</div>
						<button class="btn btn-full-red float-right">Add Customer</button>
					</div>
				</div>
			</form>
		</div>
	</div>
</template>

<script>
import Header from "@/components/Header.vue";
import Images from 'vue-material-design-icons/ImageArea.vue';
export default {
	components:{
		Header,
		Images
	},
	data() {
		return {
			
		}
	}
}
</script>

<style lang="scss" scoped>
.customers{
	background: #512DA8;
	flex: 1;
	min-height: 100vh;
	padding: 2rem;
}
.customers_container{
	background: white;
	border-radius: 8px;
}

.breadcrumb{
	ol{
		display: flex;
		li{
			position: relative;
			font-size: 24px;
			line-height: 28px;
			font-weight: 600;
			color: #F44336;
			margin-right: 20px;
			padding-right: 30px;
			
			&::after{
				content: '>';
				position: absolute;
				right: 0;
				font-size: 24px;
				font-weight: 600;
				color: black;
			}
			&.active{
				color: black;
				margin-right: 0;
				padding-right: 0;
				&::after{
					content: '';

				}
			}
			@media (max-width: 576px) {
				font-size: 14px;
				line-height: 18px;
				font-weight: 600;
			}
		}
	}
}

.add_customer_form{
	.left{
		width: 18%;
		@media (max-width: 768px) {
			width: 31%;
		}
		@media (max-width: 576px) {
			width: 100%;
			margin-bottom: 20px;
		}
		.photo{
			width: 100%;
			max-width: 280px;
			margin-left: auto;
			margin-right: auto;
			background: #e2e2e2;
			height: 210px;
			display: flex;
			justify-content: center;
			align-items: center;
			.sample{
				text-align: center;
				svg{
					margin: 0 auto;
					height: 40px;
					width: 40px;
				}
				p{
					margin: 0;
				}
			}
		}
		.form-group{
			input[type="file"]{
				display: none;
			}
			label{
				display: block;
				width: 90%;
				border-radius: 10px;
				background: #e2e2e2;
				text-align: center;
				padding: 10px;
				cursor: pointer;
				margin: 0 auto;
			}
		}
		.btn_remove{
			display: block;
			width: 90%;
			border-radius: 10px;
			background: #e2e2e2;
			text-align: center;
			padding: 10px;
			cursor: pointer;
			margin: 0 auto;
		}
	}
	.center, .right{
		width: 38%;
		@media (max-width: 768px) {
			width: 31%;
		}
		@media (max-width: 576px) {
			width: 100%;
		}
		.form-group{
			margin-bottom: 16px;
			.required{
				font-size: 12px;
				color: #F44336;
				margin: 0;
			}
			input, textarea, select{
				padding: 10px 16px;
				border-radius: 10px;
				border: 1px solid #BDBDBD;
				width: 100%;
				margin-top: 8px;
				transition: .3s;
				&:focus-visible{
					outline: 0;
					border-color: #512DA8;
				}
			}
			input::-webkit-outer-spin-button,
			input::-webkit-inner-spin-button {
				-webkit-appearance: none;
				margin: 0;
			}
			&.fit-content{
				width: fit-content;
				input[type="radio"]{
					width: 24px;
					cursor: pointer;
				}
				.label_radio{
					color: black;
					cursor: pointer;
				}
			}
			.phone{
				border-radius: 10px;
				border: 1px solid #BDBDBD;
				select{
					width: 30%;
					margin: 0;
					border: 0;
					@media (max-width: 576px) {
						width: 40%;
					}
				}
				input{
					width: 70%;
					margin: 0;
					border: 0;
					@media (max-width: 576px) {
						width: 60%;
					}
				}
			}
			
		}
		.btn{
			padding: 12px 30px;
			@media (max-width: 768px) {

			}
		}
	}
}
</style>