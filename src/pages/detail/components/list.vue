<template>
	<div>
		<div 
		class="item"
		v-for="(item,index) of DetailList"
		:key="index"
		>
		
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>
			<div class="item-children" v-if="item.children">
				<detail-list :DetailList="item.children"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
export default{
	name: 'DetailList',
	props: {
		DetailList: Array
	}
}
</script>

<style lang="stylus" scoped>

.item-title-icon
	position: relative
	display: inline-block
	width: .36rem
	height: .36rem
	top: .06rem
	left: .06rem
	background: url(https://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
	margin-right: .1rem
	background-size: .4rem 3rem
.item-title
	line-height: .8rem
	padding: 0 .2rem
	font-size: .32rem
.item-children
	padding: 0 .2rem
</style>