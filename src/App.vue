<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';
import AppSpecialties from './components/AppSpecialties.vue';

export default{
    components: { 
        AppHeader,
        AppHero,
        AppSpecialties
     }
}

</script>

<template>
    <AppHeader/>
    <AppHero/>
    <AppSpecialties/>
</template>

<style lang="scss">
@use './style/general.scss' as *;
@import "@fortawesome/fontawesome-free/css/all.css";


</style>
