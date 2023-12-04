<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';

export default{
    components: { 
        AppHeader,
        AppHero
     }
}

</script>

<template>
    <AppHeader/>
    <AppHero/>
</template>

<style lang="scss">
@import "@fortawesome/fontawesome-free/css/all.css";
@import '../src/assets/style/general.scss';

</style>
