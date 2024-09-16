<template>
	<header
		class="flex items-center justify-between border-b border-slate-100 dark:border-slate-700 -mx-6 px-6 py-[15px] mb-6">
		<div>
			<span
				class="block text-xl text-slate-900 font-medium dark:text-[#eee]"
				>Theme customizer</span
			>
			<span
				class="block text-sm font-light text-[#68768A] dark:text-[#eee]"
				>Customize & Preview in Real Time</span
			>
		</div>
		<div
			class="cursor-pointer text-2xl text-slate-800 dark:text-slate-200"
			@click="this.$store.themeSettingsStore.isOpenSettings = false">
			<Icon icon="heroicons-outline:x" />
		</div>
	</header>
</template>

<script setup>
import Icon from '@/components/Icon';
</script>
