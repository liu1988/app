<script>
	export default {
		onLaunch: function() {
            // #ifdef APP-PLUS
            plus.screen.lockOrientation('portrait-primary');
            // #endif
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>


<style>
	/*每个页面公共css */
	page {
		min-height: 100%;
		background-color: #ede8ee;
		height: 100%;
		font-size: 32px;
		line-height: 1.6;
	}
</style>

