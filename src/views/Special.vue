<template>
	<div>
	<div class="banner"><h2>全部专题</h2></div>
	<div class="container">
		<div class="box"v-for="(item, index) in specials" :key="index"><div class="in-box">
		<div class="left">
			<img :src="item.banner" />
		</div>
		<div class="right">
			<div class="flex-between" style="height: 20%; width: 100%;">
			<h3>{{item.title}}</h3>	
			<button class="low_button blue_bts">关注专题</button>	
			</div>
			<div>
				<span class="small_font">{{item.viewCount}}次浏览</span>
			</div>
			<div class="content">
				<span>{{item.introduction}}</span>
			</div>
			<span v-for="(section,index) in item.sections" :key="index"  class="title">
				{{section.sectionTitle}}
			</span>
		</div>
		</div></div>
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
		this.axios.get('http://localhost:8080/api/special/all').then(res => {
			this.specials = res.data.data;
		});
	}
};
</script>

<style scoped>
.banner {
	width: 100%;
	height: 60px;
	background: #ffffff;
	display: flex;
	align-items: center;
	justify-content: flex-start;
	margin-bottom: 10px;
}
.box{
	width: 100%;
	height: 250px;
	background: #FFFFFF;
	display: flex;
	align-items: center;
	justify-content: center;
}
.in-box{
	border-radius: 10px;
	width: 90%;
	height: 90%;
	display: flex;
	justify-content: space-between;
}
.left{
	width: 25%;
	height: 100%;
}
.left img{
	width:100%;
	height: 100%;
	border-radius: 10px;
}
.right{
	width: 73%;
	height: 100%;
}
.content{
	width: 100%;
	height: 45%;
	padding:10px;
}
.title{
	/* width: 40px;
	height: 15px; */
	background: lightgray;
	color: gray;
	font-size: 12px;
}
</style>
