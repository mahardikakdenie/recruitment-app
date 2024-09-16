<template>
	<card title="Potential Candidate">
		<template #header>
			<icon icon="tabler:dots" />
		</template>

		<div v-for="i in 4" :key="i" class="grid grid-cols-4 border-y p-4" :class="{'border-t-0': i !== 1}">
			<div class="flex px-2 border-r">
				<div class="flex items-center">
					<img :src="profileImg" alt="" width="40" />
				</div>
				<div class="ml-2">
					<div>
						<span class="text-sm font-bold">Usep Mulyadi</span>
					</div>
					<div>
						<span class="text-sm">Project Owneer</span>
					</div>
				</div>
			</div>
			<div class="px-2 border-r">
				<div><small> Location </small></div>
				<div>
					<small class="font-bold"> Bandung </small>
				</div>
			</div>
			<div class="px-2 border-r">
				<div><small> Position </small></div>
				<div>
					<small class="font-bold"> Frontend Developer </small>
				</div>
			</div>
			<div class="px-2 border-r">
				<div><small> Level </small></div>
				<div>
					<small class="font-bold"> Middler </small>
				</div>
			</div>
		</div>
	</card>
</template>

<script setup>
import Card from '@/components/Card';
import profileImg from '@/assets/images/all-img/user.png';
import Icon from '@/components/Icon';
</script>
