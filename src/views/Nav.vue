<template>
	<div>
		<div class="nav gutter">
			<div class="middle-box flex-around">
			<img src="../assets/image/font.png"/>
			<span> <router-link to="/home" class="nomal_font">首页</router-link></span>
			<span ><router-link to="/explore" class="nomal_font">发现</router-link></span>
			<span ><router-link to="/question/waiting" class="nomal_font">等你来答</router-link></span>	
			<input type="text" placeholder="劝人喝酒竟有法律风险" class="input_text"/>
			<button class="nomal_button bule_bts">提问</button>
			</div>
			<div class="small-box flex-around"  >
			<img src="../assets/image/tip.png" class="logo-img"/>
			<img src="../assets/image/message.png" class="logo-img" />
			<span><router-link to="/login" class="nomal_font">去登录</router-link></span>
			</div>
				
		</div>
		<router-view/>
	</div>
</template>

<script>
	export default{
		name:'nav',
		data(){
			return {};
		},
		created() {}
	};
</script>

<style scoped>
	.input_text{
		width: 300px;
		height: 25px;
		border-radius: 3px;
		margin-right: 8px;
		background: #f6f6f6;
	}
	.logo-img{
		width: 26px;
		height: 26px;
	}
</style>
