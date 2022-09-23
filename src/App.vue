<template>
	<div class="wrapper">
		<progress-bar
			:items="items"
			:height="height"
			:width="width"
		/>
	</div>
</template>

<script>
	import ProgressBar from "@/components/ProgressBar.vue"
	export default {
		components: {
			ProgressBar,
		},
		data() {
			return {
				items: [
					{name: 'Sold', color: '#BD1FBE', value: 677},
					{name: 'Got free', color: '#FC64FF', value: 23},
					{name: 'Burned', color: '#1de53b', value: 202},
					{name: 'Free float', color: '#9ba3aa', value: 323},
					{name: 'Test', color: '#000', value: 1},
				],
				height: 25,
				width: 8,
			}
		}
	}
</script>

<style lang="scss">
/*NULL STYLE*/
*{padding: 0;margin: 0;border: 0;}
*,*:before,*:after{-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;}
:focus,:active{outline: none;}
a:focus,a:active{outline: none;}
nav,footer,header,aside{display: block;}
html,body{height:100%;width:100%;font-size:100%;line-height:1;font-size:16px;-ms-text-size-adjust:100%;-moz-text-size-adjust:100%;-webkit-text-size-adjust:100%;}
input,button,textarea{font-family:inherit;}
input::-ms-clear{display: none;}
button{cursor: pointer;}
button::-moz-focus-inner{padding:0;border:0;}
a,a:visited{text-decoration: none;}
a:hover{text-decoration: none;}
ul li{list-style: none;}
img{vertical-align: top;}
h1,h2,h3,h4,h5,h6{font-size:inherit;font-weight: inherit;}
/*--------------------*/
.wrapper {
	overflow: hidden;
	min-height: 100vh;
	padding: 15px;
}
</style>