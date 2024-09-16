<template>
    <div>
        <div>
            <Card title="Upcomming Interview" title-class="text-xs">
                <template #header>
                    <icon icon="tabler:dots" />
                </template>

                <!-- Body -->
                <div class="grid grid-cols-4">
                    <div class="flex px-2 border-r">
                        <div class="flex items-center">
                            <img :src="profileImg" alt="" width="40">
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
                    <div class="pl-2 border-r">
                        <div>
                            <span>Timeline</span>
                        </div>
                        <div>
                            <span class="text-xs font-bold">
                                2:30 AM - 3.30 AM
                            </span>
                        </div>
                    </div>
                    <div class="pl-2 border-r">
                        <div>
                            <span class="text-sm">
                                Current Company
                            </span>
                        </div>
                        <div>
                            <span class="text-sm font-bold">
                                Tokopedia
                            </span>
                        </div>
                    </div>
                    <div class="flex px-4 items-center justify-center gap-3">
                        <VueButton 
                            text="View Resume" 
                            btn-class="btn btn-sm border" 
                        />
                        <VueButton 
                            text="Join Meeting" 
                            btn-class="btn btn-sm bg-green-900 text-white" 
                        />
                    </div>
                </div>
            </Card>
        </div>
    </div>
</template>

<script setup>
import Card from '@/components/Card';
import Icon from '@/components/Icon';
import profileImg from "@/assets/images/all-img/user.png";
import VueButton from '@/components/Button';
</script>
