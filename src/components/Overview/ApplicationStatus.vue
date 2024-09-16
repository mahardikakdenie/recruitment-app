<template>
    <card title="Application Status">
        <template #header>
            <icon icon="tabler:dots" />
        </template>

        <div class="grid grid-cols-3 gap-4">
            <card v-for="(summary, i) in summaries" :key="i" className="border" body-class="p-2">
                <div class="flex">
                    <div class="flex items-center justify-center pl-0 w-10">
                        <icon :icon="summary.icon" class="text-[30px] text-green-600" />
                    </div>
                    <div class="px-4 m-auto">
                        <div>
                            <small class="font-bold">{{ summary.label }}</small>
                        </div>
                        <div>
                            <small class="">{{ summary.value }} Application</small>
                        </div>
                    </div>
                </div>

                <!-- Footer -->
                <div class="border-t mt-4 px-0 text-sm text-gray-600 dark:text-gray-400">
                    <div class="flex justify-between">
                        <div class="flex items-center">
                            <small class="text-green-600">View All</small>
                        </div>
                        <vue-button icon="radix-icons:external-link" btn-class="btn btn-sm text-sm" icon-class="text-sm text-green-600" />
                    </div>
                </div>
            </card>
        </div>
    </card>
</template>

<script setup>
import Card from '@/components/Card';
import Icon from '@/components/Icon';
import VueButton from '@/components/Button';
import { ref } from 'vue';

const summaries = ref([
    {
        label: 'New Application',
        key: 'new-application',
        icon: 'mi:document',
        value: 10,
    },
    {
        label: 'In Review',
        key: 'in-review',
        icon: 'fa6-solid:arrows-rotate',
        value: 10,
    },
    {
        label: 'Interview',
        key: 'interview',
        icon: 'vaadin:chat',
        value: 10,
    },
    {
        label: 'Offers',
        key: 'offers',
        icon: 'icon-park-solid:doc-detail',
        value: 10,
    },
    {
        label: 'Hired',
        key: 'hired',
        icon: 'ep:document-checked',
        value: 10,
    },
    {
        label: 'Reject',
        key: 'reject',
        icon: 'fluent:document-dismiss-24-filled',
        value: 10,
    },
]);
</script>
