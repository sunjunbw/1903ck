<template>
  <div class="about">
      <input type="text" v-model="username" />
      <input type="text" v-model="password" />
 	  <button @click="login">登录</button>
  </div>
</template>
<script>

import { Toast} from 'mint-ui';
export default {
	data(){
		return {
			username:'',
			password:''
		}
	},
	methods:{
		login(){
			this.$axios.post("/hd/users/login",
				{
					username:this.username,
					password:this.password
				},
				{
				"headers":{
					"Content-type":"application/json"
				}
			}).then((res)=>{
					if(res.data.data){
						Toast({
							message:'登录成功',
							position:'middle',
							duration:1500
						})
					}
					else{
						Toast({
							message:'登录失败',
							position:'middle',
							duration:1500
						})
					}
			})
		}
		
	}
}

</script>
<style>
	.mint-swipe{
		height:2rem!important;
		background: #ccc;
		
	}
	.mint-tab-container{
		height: 2rem!important;
	}
</style>
