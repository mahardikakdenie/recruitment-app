<template>
    <div>
        <UpcommingInterview />
        <div class="mt-3 grid grid-cols-3 gap-2">
            <div class="col-span-2">
                <ApplicationStatus />
            </div>
            <div class="">
                <ApplicationSource />
            </div>
        </div>

        <div class="mt-3 grid grid-cols-3 gap-2">
            <div class="col-span-2">
                <PotentialCandidate />
            </div>
            <div>
                <CurrentVacancies />
            </div>
        </div>
    </div>
</template>

<script setup>
import UpcommingInterview from '@/components/Overview/UpcommingInterview.vue';
import ApplicationStatus from '@/components/Overview/ApplicationStatus.vue';
import ApplicationSource from '@/components/Overview/ApplicationSource.vue';
import PotentialCandidate from '@/components/Overview/PotentialCandidate.vue';
import CurrentVacancies from '@/components/Overview/CurrentVacancies.vue';
</script>
