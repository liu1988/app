<template>
	<view class="register">
		<view class="register_Title">
			欢迎来到你的报应
		</view>
		<view class="register-button">
			<text class="register-text">手机号登录注册</text>
		</view>
		<view class="register-input">
			<view class="input-phone">
				<view class="phone_index">
					<text class="phone_index_hm">+86</text>
					<uni-icons type="arrowdown" size="18"></uni-icons>
				</view>
				<input @input="inputFunction" type="number" v-model="number" class="phone_number" placeholder-class="phone_number_index"
				 placeholder="请输入手机号" />
			</view>
			<view class="dialog-bd">
				<!-- <view class="code-view"> -->
				<!-- <input placeholder-class="phone_number_yanzheng" type="text" placeholder="请输入6位验证码" /> -->
				<!-- <input v-for="(code,index) of codeAry" :v-key="index" class="code-item" type="number" :value="code.val" /> -->
				<!-- <view v-for="(code,index) of codeAry" :v-key="index" class="code-item">{{code.val}}</view> -->
				<!-- </view> -->
				<view class="dialog_yzm">
					<input type="number" placeholder-class="dialog_yzm_index" value="" placeholder="请输入6位验证码" />
				</view>
				<button class="dialog_yzm_text" hover-class="btn_text_hq">点击获取</button>
			</view>
		</view>
		<view class="register-Password">
			<text class="Password-text">密码登录</text>
			<text class="Password-Tourist">游客登录</text>
		</view>
		<view class="login_btn">
			<button @click="Verification" class="btn_text" hover-class="btn_text_ai">下一步</button>
		</view>
	</view>
</template>

<script>
	import uniIcons from "@dcloudio/uni-ui/lib/uni-icons/uni-icons.vue"
	export default {
		components: {
			uniIcons
		},
		data() {
			return {
				codeAry: [{
					"val": "1"
				}, {
					"val": "2"
				}, {
					"val": "3"
				}, {
					"val": "4"
				}, {
					"val": "5"
				}, {
					"val": ""
				}],
				number: ""
			}
		},
		methods: {
			Verification() {
				console.log(this.number)
				uni.reLaunch({
				    url: '../index/index',
				})
			},
			inputFunction() {
				this.$nextTick(() => {
					if (this.number.length >= 11) {
						this.number = this.number.slice(0, 11)
					}
					if (this.number.length === 11) {
						if ((/^[1][3,4,5,7,8][0-9]{9}$/.test(this.number))) {
							console.log("手机号码正确");
						} else {
							this.number = ""
						}
					}
				})

			},
		},

	}
</script>

<style>
	.register {
		width: 600rpx;
		margin: 0 auto;
	}

	.register_Title {
		text-align: center;
		font-size: 23px;
		margin: 30px 0 25px 0;
	}

	.register-button {
		margin-bottom: 20px;
	}

	.register-text {
		letter-spacing: 1px;
		font-size: 28px;
		line-height: 30px;
	}

	.input-phone {
		height: 30px;
		border-bottom: 1px solid #ccc;
		margin-bottom: 15px;
	}

	.dialog_yzm {
		width: 450rpx;
		height: 33px;
		border-bottom: 1px solid #ccc;
		float: left;
	}

	.phone_index_hm {
		margin-right: 3px;
	}

	.phone_index {
		float: left;
		font-size: 14px;
	}

	.phone_number_index {
		font-size: 14px;
	}

	.phone_number {
		float: left;
		margin-left: 15px;
	}

	.dialog-bd {
		height: 25px;
	}

	.code-view {
		height: 25px;
		display: block;
		text-align: center;
	}

	.code-item {
		float: left;
		margin-right: 10px;
		border-bottom: 1px solid #1726cc;
		/* #ccc */
		width: 35px;
		height: 25px;
		font-size: 16px;
	}

	.phone_number_yanzheng {
		text-align: left;
		font-size: 14px;
	}

	.register-Password {
		overflow: hidden;
		margin-top: 20px;
	}

	.Password-text {
		color: #398ce6;
		float: left;
		font-size: 14px;
	}

	.Password-Tourist {
		color: #398ce6;
		float: right;
		font-size: 14px;
	}

	.login_btn {

		margin: 0 auto;
		margin-top: 25px;
	}

	.btn_text {
		width: 280px;
		height: 36px;
		font-size: 16px;
		background: #fc6ea2;
		color: #FFF;
		line-height: 36px;
		display: block;
		border-radius: 5px;
		box-shadow: 0px 1px 1px #d8d8d8;
	}

	.btn_text[disabled] {
		background: #f98ab3;
		color: #fff;
	}

	.btn_text_ai {
		background: #e85088;
	}

	.dialog_yzm_index {
		width: 450rpx;
		font-size: 14px;
	}

	.dialog_yzm_text {
		display: block;
		width: 120rpx;
		height: 34px;
		background-color: #4ec2ff;
		font-size: 12px;
		text-align: center;
		line-height: 34px;
		float: right;
		color: #fff;
		padding: 0;
	}
	.btn_text_hq{
		background: #3eabe4;
	}
</style>
