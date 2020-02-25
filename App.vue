<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
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
	.page {
		height: 100%;
		width: 100%;
		background: #fafafa;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
	}
</style>
