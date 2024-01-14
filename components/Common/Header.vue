<template>
	<div class="w-full bg-white sticky top-0 z-[110]">
		<div
			id="fre123-header"
			class="header-transition m-auto flex border-b-2 border-b-gray-50 md:px-[20px] py-[15px]"
		>
			<div class="flex md:basis-1/3 relative">
				<a :href="baseInfo['host']" target="_blank">
					<img class="header-logo header-transition ml-[20px]" :src="baseInfo['logo']" alt="" />
				</a>
				<a
					:href="baseInfo['host']"
					target="_blank"
					class="header-text header-transition ml-[10px] leading-[80px] md:text-[22px] text-[#333]"
				>
					{{ baseInfo['app_name'] }}
				</a>
			</div>

			<div
				v-show="showSearch"
				class="flex-grow hidden md:flex items-center justify-center cursor-pointer"
			>
				<IndexSearch> </IndexSearch>
			</div>
			<div class="cursor-pointer hidden md:flex basis-1/3 items-center justify-end"></div>
		</div>
	</div>
</template>

<script setup lang="ts">
import { CONFIG_KEY_BASE, getConfigItem } from '~/stores/config'
const baseInfo = getConfigItem(CONFIG_KEY_BASE)

withDefaults(
	defineProps<{
		isIndex: boolean
		showSearch?: boolean
		headerText?: string
	}>(),
	{
		showSearch: false,
	},
)

// 控制头部变化
const headerAnimation = (action: string) => {
	const headerDom = document.getElementById('fre123-header')
	if (headerDom) {
		if (action == 'smaller') {
			headerDom.classList.add('custom-size')
		} else {
			headerDom.classList.remove('custom-size')
		}
	}
}

const isShow = ref(false)
const showCategory = (show: boolean) => {
	isShow.value = show
}

defineExpose({ headerAnimation })
</script>

<style scoped>
#fre123-header {
	box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
}
.header-transition {
	transition: all 0.3s ease-in-out;
}

.header-logo {
	width: 80px;
	height: 80px;
}

.header-logo:hover {
	transform: rotate(360deg);
}

/* 头部固定类 */
.custom-size {
	padding-top: 0px;
	padding-bottom: 0px;
	box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.custom-size img {
	width: 60px;
	height: 60px;
}

.custom-size .header-text {
	height: 60px;
	line-height: 60px;
	font-size: 22px;
}
</style>
