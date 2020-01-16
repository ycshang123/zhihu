<template>
	<div class="container">
		<div class="logo"><h2>最新专题</h2></div>
		<div class="flex">
			<div class="table" v-for="(item, index) in specials" :key="index">
				<div class="cover"><img :src="item.banner" /></div>
				<div class="text">
					<div class="left">
						<h2>{{ item.title }}</h2>
						<span class="small_font">{{ item.viewCount }}浏览</span>
					</div>
					<div class="right"><button class="low_button blue_bts">关注专题</button></div>
				</div>
				<div>{{ item.introduction }}</div>
			</div>
		</div>
		<div class="flex-center">
			<router-link to="special/all">
			<button class="big_button gray_bts">查看更多专题</button>	
			</router-link>
			
		</div>
		
	</div>
</template>

<script>
export default {
	data() {
		return {
			specials: []
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/special').then(res => {
			this.specials = res.data.data;
		});
	}
};
</script>

<style scoped>
.logo {
	height: 50px;
}
.table {
	width: 45%;
	height: 400px;
	border-radius: 10px;
	background: #FFFFFF;
}
.cover {
	width: 100%;
	height: 60%;
}
.cover img {
	width: 100%;
	height: 80%;
	border-radius: 10px;
}
.text {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-left: 20px;
}
</style>
