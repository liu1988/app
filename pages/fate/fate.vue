<template>
    <view class="relative" @touchmove="handleTouchMove" @touchstart="handleTouchStart" @touchend="handleTouchEnd">
        <view class="img"  v-for="(img,index) in imgSrc" :key="index">
            <image :src="img" mode=""></image>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                flag: 0,
                text: '',
                lastX: 0,
                lastY: 0,
                imgSrc:[
                    "http://localhost:8888/app/fate/1.jpg",
                    "http://localhost:8888/app/fate/2.jpg",
                    "http://localhost:8888/app/fate/3.jpg",
                    "http://localhost:8888/app/fate/4.jpg",
                    "http://localhost:8888/app/fate/5.jpg"
                ]
            }
        },
        onLoad() {

        },
        methods: {
            handleTouchMove: function(event) {
                if (this.flag !== 0) {
                    return;
                }
                let currentX = event.touches[0].pageX;
                let currentY = event.touches[0].pageY;
                let tx = currentX - this.lastX;
                let ty = currentY - this.lastY;
                let text = '';
                this.mindex = -1;
                //左右方向滑动
                if (Math.abs(tx) > Math.abs(ty)) {
                    if (tx < 0) {
                        text = '向左滑动';
                        this.flag = 1;
                        //  this.getList();  //调用列表的方法
                    } else if (tx > 0) {
                        text = '向右滑动';
                        this.flag = 2;
                    }
                }
                //上下方向滑动
                else {
                    if (ty < 0) {
                        text = '向上滑动';
                        this.flag = 3;
                        //  this.getList();  //调用列表的方法
                    } else if (ty > 0) {
                        text = '向下滑动';
                        this.flag = 4;
                    }
                }
                //将当前坐标进行保存以进行下一次计算
                this.lastX = currentX;
                this.lastY = currentY;
                this.text = text;
            },
            handleTouchStart: function(event) {
                this.lastX = event.touches[0].pageX;
                this.lastY = event.touches[0].pageY;
            },
            handleTouchEnd: function(event) {
                this.flag = 0;
                this.text = '没有滑动';
            },
        }
    }
</script>

<style>

</style>
