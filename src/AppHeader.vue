<script>
import HeaderTopComponent from './components/HeaderTopComponent.vue';
import HeaderBottomComponent from './components/HeaderBottomComponent.vue';

export default {
    name: 'AppHeader',
    components: {
        HeaderTopComponent,
        HeaderBottomComponent,
    },
};
</script>

<template>
    <header>
        <HeaderTopComponent />
        <HeaderBottomComponent />
    </header>
</template>

<style lang="scss" scoped>
@use './style/partials/variables' as *;
header {
    position: fixed;
    width: 100vw;
    height: 155px;
    z-index: 999;
    background-color: $white;
}
</style>
