<template>
	<div>
		<div class="grid grid-cols-3">
			<a href="https://www.huya.com/wuhushenkp" target="_blank">
				<img :src="safeResolve('/wuhushen.jpg')" class="logo" />
			</a>
			<a href="https://www.huya.com/941103" target="_blank">
				<img :src="safeResolve('/gushouyu.jpg')" class="logo" />
			</a>
			<a href="https://www.huya.com/924898" target="_blank">
				<img :src="safeResolve('/caiqi.jpg')" class="logo vue" />
			</a>
		</div>
		<HelloWorld msg="Tov + Vite + Vue" />
	</div>
</template>

<style>
a {
	color: rgba(37, 99, 235);
}

p {
	padding: 0 10px;
}

.logo {
	width: 10em;
	height: 10em;
	padding: 1.5rem;
	will-change: filter;
	transition: filter 300ms;
}
.logo:hover {
	filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
	filter: drop-shadow(0 0 2em #df51bbaa);
}
</style>
