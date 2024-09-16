<template>
    <Card title="overview">
        <template #header>
            <icon icon="tabler:dots" />
        </template>
        <apexchart type="radialBar" :height="300" :options="MultipleRadialbars.chartOptions"
            :series="MultipleRadialbars.series" />
    </Card>
</template>

<script setup>
import {
    MultipleRadialbars,
} from "@/constant/appex-chart";

import Card from '@/components/Card';
import Icon from '@/components/Icon';
</script>
