<script>
import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
import AppFooter from './AppFooter.vue';

export default {
    name: 'App',
    components: {
        AppHeader,
        AppMain,
        AppFooter,
    },
};
</script>

<template>
    <AppHeader />
    <AppMain />
    <AppFooter />
</template>

<style lang="scss">
@use './style/general';
</style>
