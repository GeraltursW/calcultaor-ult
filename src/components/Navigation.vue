<script setup lang="ts">
import { getRoutes } from '@/plugins/router'
import { SwitchIcon } from 'vue-dark-switch'

const { te, t } = useI18n()

const routes = getRoutes()
	.filter((r) => !r.path.includes('notFound'))
	.map((r) => {
		let { path, name } = r
		if (path === safeResolve('/')) {
			return { path, name: 'home' }
		}

		if (!name) {
			name = path
		}

		return { path, name: name.toString().slice(1).replaceAll('/', ' · ') }
	})
</script>

<template>
	<nav
		aria-label="Site Nav"
		class="mx-auto h-80px max-w-3xl flex items-center justify-between p-4"
	>
		<div class="flex items-center justify-center space-x-5">
			<SwitchIcon unmount-persets />
			<a href="https://www.huya.com/wuhushenkp" target="_blank">
				<span
					style="
						color: white;
						font-size: 14px;
						border-radius: 3px 0 0 3px;
						padding: 4px 4px 4px 4px;
						background: #00b894;
					"
					>芜湖园区</span
				>
				<span
					style="
						border-radius: 0 3px 3px 0;
						padding: 5px 10px 5px 2px;
						background: #00dc8220;
						font-size: 13px;
					"
				>
					https://www.huya.com/wuhushenkp
				</span>
			</a>
		</div>

		<ul class="flex items-center gap-2 text-sm font-medium">
			<li v-for="r of routes" :key="r.path" class="hidden !block">
				<RouterLink class="rounded-lg px-3 py-2" :to="r.path">
					{{ te(r.name) ? t(r.name) : r.name }}
				</RouterLink>
			</li>

			<li class="hidden !block">
				<Dropdown />
			</li>
		</ul>
	</nav>
</template>
