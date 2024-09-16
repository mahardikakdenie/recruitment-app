<template>
    <div :class="`
					logo-wrapper ${siebarIsCollaps} ${isLogoWrapperWhen} ${themeSkinIsHovered ? 'logo-hovered' : ''}
				`">
        <router-link :to="{ name: 'home' }" v-if="isSidebarOpenOrMouseHovered">
            <img src="@/assets/images/logo/logo.svg" alt="" v-if="
                !this.$store.themeSettingsStore.isDark &&
                !this.$store.themeSettingsStore.semidark
            " />

            <img src="@/assets/images/logo/logo-white.svg" alt="" v-if="
                this.$store.themeSettingsStore.isDark ||
                this.$store.themeSettingsStore.semidark
            " />
        </router-link>
        <router-link :to="{ name: 'home' }" v-if="isSidebarCollapsedAndNotHovered">
            <img src="@/assets/images/logo/logo-c.svg" alt="" v-if="
                !this.$store.themeSettingsStore.isDark &&
                !this.$store.themeSettingsStore.semidark
            " />
            <img src="@/assets/images/logo/logo-c-white.svg" alt="" v-if="
                this.$store.themeSettingsStore.isDark ||
                this.$store.themeSettingsStore.semidark
            " />
        </router-link>
        <span class="cursor-pointer text-slate-900 dark:text-white text-2xl" v-if="isSidebarOpenOrMouseHovered
        " @click="
            this.$store.themeSettingsStore.sidebarCollasp =
            !this.$store.themeSettingsStore.sidebarCollasp
            ">
            <!-- <Icon icon="heroicons-outline:menu-alt-3"
        /> -->
            <div class="h-4 w-4 border-[1.5px] border-slate-900 dark:border-slate-700 rounded-full transition-all duration-150"
                :class="this.$store.themeSettingsStore.sidebarCollasp
                    ? ''
                    : 'ring-2 ring-inset ring-offset-4 ring-black-900 dark:ring-slate-400 bg-slate-900 dark:bg-slate-400 dark:ring-offset-slate-700'
                    "></div>
        </span>
    </div>
</template>


<script>
// import { Icon } from "@iconify/vue";
import { defineComponent } from "vue";
import { menuItems } from "../../constant/data";
import Navmenu from "./Navmenu";
import { gsap } from "gsap";
import { SimpleBar } from "simplebar-vue3";
import { ref, onMounted } from "vue";

export default defineComponent({
    components: {
        // Icon,
        Navmenu,
        SimpleBar,
    },
    data() {
        return {
            menuItems,
            openClass: "w-[248px]",
            closeClass: "w-[72px] close_sidebar",
        };
    },

    computed: {
        sidebarIsCollasp() {
            return this.$store.themeSettingsStore.sidebarCollasp;
        },
        themeSkinIsBordered() {
            return this.$store.themeSettingsStore.skin === 'bordered';
        },
        siebarIsCollaps() {
            return this.sidebarIsCollasp ? this.closeClass : this.openClass;
        },
        themeSkinIsHovered() {
            return this.$store.themeSettingsStore.isMouseHovered;
        },
        borderedClass() {
            return 'border-r border-gray-5002 dark:border-slate-700';
        },
        sidebarIsBordered() {
            const isBordered = this.themeSkinIsBordered;
            const borderedClass = this.borderedClass;

            return isBordered ? borderedClass : 'shadow-base'
        },
        sideBarIsHovered() {
            return this.themeSkinIsHovered ? 'sidebar-hovered' : ''
        },
        isSidebarOpenOrMouseHovered() {
            return !this.sidebarIsCollasp || this.themeSkinIsHovered
        },
        isSidebarCollapsedAndNotHovered() {
            return this.sidebarIsCollasp && !this.themeSkinIsHovered
        },
        isLogoWrapperWhen() {
            return this.themeSkinIsBordered ? `border-b ${this.borderedClass}` : ' border-none'
        },
    },

    setup() {
        const shadowbase = ref(false);
        const simplebarInstance = ref(null);
        onMounted(() => {
            simplebarInstance.value
                .getScrollElement()
                .addEventListener("scroll", () => {
                    if (simplebarInstance.value.getScrollElement().scrollTop > 50) {
                        simplebarInstance.value.getScrollElement().classList.add("scroll");
                        shadowbase.value = true;
                    } else {
                        simplebarInstance.value
                            .getScrollElement()
                            .classList.remove("scroll");
                        shadowbase.value = false;
                    }
                });
        });

        return {
            simplebarInstance,
            shadowbase,
        };
    },
});
</script>
