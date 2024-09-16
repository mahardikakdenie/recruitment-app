<template>
	<card title="Current Vacancies">
		<template #header>
			<icon icon="tabler:dots" />
		</template>

		<div v-for="i in 4" :key="i" class="border-y p-4">
			<div>
				<span> UI/UX - Senior Level </span>
			</div>
			<div class="grid grid-cols-2 mt-2">
				<div class="border-r flex">
					<icon icon="ic:sharp-location-city" />
					<small> Jakarta Branch Office </small>
				</div>
				<div class="flex ml-3">
					<icon icon="codicon:account" />
					<small> 0/2 Recruited </small>
				</div>
			</div>
		</div>
	</card>
</template>

<script setup>
import Card from '@/components/Card';
import Icon from '@/components/Icon';
</script>
