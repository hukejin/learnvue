<template>
	<div class="timeline">
		<div class="baseline">
			<div v-for="(item,index) in items" class="itemcop" @click="itemclick(index)">
				<div class="item" v-if="index % 2 === 0">
					<div class="circle"></div>
					<div class="content">{{item.time}}</div>
				</div>
				<div class="itemconver" v-else>
					<div class="contentconver">{{item.time}}</div>
					<div class="circle"></div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: "timeline",
		data() {
			return {
				items:[],
			}
		},
		mounted() {
			for (let i = 0; i < 24; i++) {
				let time = i<10 ? ('0'+i):(i);
				time = time + ":00";
				this.items.push({'time':time})
			}
		},
		computed: {},
		watch: {},
		components: {},
		methods: {
			itemclick(index){
				this.$emit('itemdown',index)
			}
		},
		props: []
	}
</script>
<style scoped>
	.timeline{
		/*width: initial;*/
		background-color: red;
		min-height: 60px;
		box-sizing: border-box;
		display: flex;
		align-items: center;
		position: relative;
		justify-content: space-between;
		flex: 1;
	}
	.baseline{
		/*width: 100%;*/
		height: 3px;
		border-radius: 3px;
		background-color: #00ff00;
		display: flex;
		justify-content: space-between;
		flex: 1;
	}
	.item{
		float: left;
		width: 60px;
		height: 60px;
		margin: auto 0;
		display: flex;
		box-sizing: border-box;
		flex-direction: column;
		align-items: center;
	}
	.circle{
		width: 11px;
		height: 11px;
		border-radius: 100%;
		background-color: indianred;
		position: absolute;
		top:50%;
		transform: translateY(-50%);
	}
	.content{
		position: absolute;
		bottom: 1px;
		font-size: 12px;
	}
	.itemconver{
		float: left;
		width: 60px;
		height: 60px;
		display: flex;
		box-sizing: border-box;
		flex-direction: column;
		align-items: center;
	}
	.contentconver{
		position: absolute;
		top: 1px;
		font-size: 12px;
	}
	.baseline::after{
		content: "";
		clear: both;
	}
	.itemcop{
		display: inline-block;
		flex: 1;
	}
</style>
