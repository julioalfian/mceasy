<template>
	<div class="pagination">
		<ul class="flex">
			<li class="prev flex items-center disabled">
				<ArrowLeft/>
				<p>Prev</p>
			</li>
			<li class="active">
				1
			</li>
			<li>
				2
			</li>
			<li>
				3
			</li>
			<li>
				4
			</li>
			<li>
				5
			</li>
			<li class="next flex items-center">
				<p>Prev</p>
				<ArrowRight/>
			</li>
		</ul>
	</div>
</template>

<script>
import ArrowLeft from 'vue-material-design-icons/ChevronLeft.vue';
import ArrowRight from 'vue-material-design-icons/ChevronRight.vue';
export default {
	components:{
		ArrowLeft,
		ArrowRight,
	}
}
</script>