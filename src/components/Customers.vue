<template>
	<div class="customers">
		<Header title="Customer" subTitle="Manage your customers here"/>
		<div class="customers_container mt-4">
			<div class="customers_head flex justify-between items-center px-4 py-5 border-b flex-wrap">
				<h4>Cutomers List</h4>
				<div class="from-group flex flex-end">
					<input type="text" placeholder="Search customers" class="search_input" v-model="findSearch">
					<div class="btn_search">
						<Search/>
					</div>
				</div>
			</div>
			<div class="customers_body py-4">
				<div class="customers_body_top flex justify-between items-center px-4 flex-wrap">
					<div class="customer_filter flex items-center flex-wrap">
						<div class="form-group">
							<label for="gender" class="mr-2">Gender</label>
							<select name="gender" id="gender" v-model="findGender">
								<option value="">All Gender</option>
								<option value="female">Female</option>
								<option value="male">Male</option>
							</select>
							<ArrowDown/>
						</div>
						<div class="form-group flex items-center lg:ml-6 ml-0 mt-2 lg:mt-0 ">
							<label for="address" class="mr-2">Address</label>
							<input type="text" class="address_input" id="address" placeholder="All country, provice, city, region, postal code" v-model="findAddress">
							<ArrowDown/>
						</div>
					</div>
					<router-link to="/addcustomer">
						<div class="btn btn-full-red flex mt-2 lg:mt-0">
							<Plus/>
							<div class="text ml-2">Add Customer</div>
						</div>
					</router-link>
				</div>
				<div class="table_container">
					<table class="w-full table-fixed mt-6">
						<thead class="border-b border-t">
							<tr>
								<th class="w-12 text-center">
									<input type="checkbox" class="select_all">
								</th>
								<th class="w-1/12 text-left">ID</th>
								<th class="w-2/12 text-left">Name</th>
								<th class="w-2/12 text-left">Gender</th>
								<th class="w-4/12 text-left">Address</th>
								<th class="w-2/12 text-left">Phone</th>
								<th class="w-1/12 text-left">Actions</th>
							</tr>
						</thead>
						<tbody>
							<tr class="border-b" v-for="item in handleFilter" :key="item.id">
								<td class="text-center">
									<input type="checkbox" class="select_item">
								</td>
								<td class="elipsis-1">{{item.id}}</td>
								<td class="elipsis-1">{{item.name}}</td>
								<td>{{item.gender}}</td>
								<td class="elipsis-1">{{item.address}}</td>
								<td class="elipsis-1">{{item.phone}}</td>
								<td class="flex">
									<div class="edit lg:mr-4 mr-1">
										<Edit/>
									</div>
									<div class="remove">
										<Remove/>
									</div>
								</td>

							</tr>
							
						</tbody>
					</table>
				</div>
				<div class="customer_filter filter_bottom flex justify-between items-center mt-12 px-5 flex-wrap">
					<div class="showing flex items-center md:mb-0 mb-4 ">
						<div class="form-group">
							<label for="showing" class="mr-2 regular">Showing</label>
							<select name="showing" id="showing">
								<option value="10">10</option>
								<option value="20">20</option>
								<option value="50">50</option>
								<option value="100">100</option>
							</select>
							<ArrowDown/>
						</div>
						<div class="ml-2">of 100</div>
					</div>
					<Pagination/>

				</div>
			</div>
		</div>
	</div>
</template>

<script>
import Header from "@/components/Header.vue";
import Pagination from "@/components/Pagination.vue";
import Search from 'vue-material-design-icons/Magnify.vue';
import Plus from 'vue-material-design-icons/Plus.vue';
import ArrowDown from 'vue-material-design-icons/ChevronDown.vue';
import Edit from 'vue-material-design-icons/PencilOutline.vue';
import Remove from 'vue-material-design-icons/DeleteOutline.vue';
//import Sort from 'vue-material-design-icons/Sort.vue';
export default {
	components:{
		Header,
		Pagination,
		Search,
		Plus,
		ArrowDown,
		Edit,
		Remove,
		
		//Sort.
	},
	data() {
		return {
			findSearch: '',
			findGender: '',
			findAddress: '',
			customer: [
				{
					select: false,
					id: '00001',
					name: 'Nabile Aqmarina',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00002',
					name: 'Nabile Qomaria',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00003',
					name: 'Naswa Shihap',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00004',
					name: 'Laila Nur',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00005',
					name: 'Amalia Putri',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00006',
					name: 'Nabila Shaqib',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00007',
					name: 'Aqmarina',
					gender: 'Female',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00008',
					name: 'Abdul Rahman',
					gender: 'Male',
					address: 'Taman Sidoarjo No 5, Sidoarjo, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00009',
					name: 'Fatih',
					gender: 'Male',
					address: 'Taman Sidoarjo No 5, Surabaya, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
				{
					select: false,
					id: '00010',
					name: 'Fajar Abdusalam',
					gender: 'Male',
					address: 'Taman Sidoarjo No 5, Lamongan, Jawa Timur, Indonesia',
					phone: '+628512345678'
				},
			]
		}
	},
	computed:{
		handleFilter(){
			if(this.findSearch){
      	return this.customer.filter((item)=>{
        return this.findSearch.toLowerCase().split(' ').every(v => item.name.toLowerCase().includes(v))
      })
      }else if(this.findGender){
      	return this.customer.filter((item)=>{
        return this.findGender.toLowerCase().split(' ').every(v => item.gender.toLowerCase().includes(v))
      })
      }else if(this.findAddress){
      	return this.customer.filter((item)=>{
        return this.findAddress.toLowerCase().split(' ').every(v => item.address.toLowerCase().includes(v))
      })
      }else{
        return this.customer;
      }
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
.from-group{
	.search_input{
		background: #f1f1f1;
		border-radius: 10px 0 0 10px;
		width: 100%;
		min-width: 400px;
		padding: 6px 16px;
		font-size: 14px;
		@media (max-width: 768px) {
			min-width: unset;
		}
		&:focus-visible{
			outline: none !important;
		}
	}
	.btn_search{
		background: #f1f1f1;
		border-radius: 0 10px 10px 0;
		cursor: pointer;
		padding: 10px;
	}
	
}
.customer_filter{
	.form-group{
		position: relative;
		@media (max-width: 768px) {
			width: 100%;
		}
		label{
			color: black;
			font-weight: 600;
			&.regular{
				font-weight: 400;
				color: #757575;;
			}
		}
		select{
			cursor: pointer;
			padding: 10px 16px ;
			padding-right: 36px;
			border: 1px solid #BDBDBD;
			border-radius: 10px;
			appearance: none;
		}
		.chevron-down-icon{
			position: absolute;
			top: 12px;
			right: 10px;
		}
		.address_input{
			background: #ffffff;
			border: 1px solid #BDBDBD;
			border-radius: 10px;
			width: 100%;
			min-width: 400px;
			padding: 10px 16px;
			padding-right: 34px;
			font-size: 14px;
			@media (max-width: 768px) {
				min-width: unset;
			}
			&:focus-visible{
				outline: none !important;
			}
		}
	}
}
.table_container{
	overflow-x: auto;
	width: 100%;
}
table{
	thead{
		th{
			padding: 12px 0;
		}
	}
	tbody{
		tr{
			transition: .3s;
			&:hover{
				background: #eeeeee;
			}
		}
		td{
			padding-top: 12px;
			padding-bottom: 16px;
			.edit, .remove{
				cursor: pointer;
				@media (max-width: 768px) {
					svg{
						width: 16px;
					}
				}
			}
		}
	}
}
</style>