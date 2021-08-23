<template>
    <view class="container">
        姓名<input v-model="name" placeholder="点此编辑姓名" >
        <br>
        年龄<input v-model="age" placeholder="点此编辑年龄" >
        <br>
        <button type="default" @click="test">提交</button>
		<button type="default" @click="test1">跳转</button>
        <view>{{name}}</view>
        <view>{{age}}</view>
        <view>{{ result }}</view>
		<view>{{ result1 }}</view>
    </view>
</template>

<script>
    var testModule = uni.requireNativePlugin("Hik-Video-Module");
    export default {
        data() {
            return {
                name:"",
                age:"",
                result:"暂未提交",
				result1:"暂未提交"
            }
        },
        methods: {
            test(){
                testModule.testText({
                    'name':this.name,
                    'age':this.age,
                },
                (ret) =>{
                    this.result="[提交反馈]"+ret.code;
                })
            },
			test1(){
				testModule.gotoPreviewActivity({
					'previewUri':this.name,
					'cameraCode':'129e41335b704ee5b0f24aa6bfba64b6'
				})
			}
        }
    }
</script>



<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
