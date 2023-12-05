<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';
import AppSpecialties from './components/AppSpecialties.vue';
import EventsSection from './components/EventsSection.vue';
import TeamSection from './components/TeamSection.vue';
import CreativeSection from './components/CreativeSection.vue';
import AppNews from './components/AppNews.vue';

export default {
    components: {
    AppHeader,
    AppHero,
    AppSpecialties,
    TeamSection,
    EventsSection,
    CreativeSection,
    AppNews
}
}

</script>

<template>
    <AppHeader />
    <AppHero />

    <div class="top-container">
        <AppSpecialties />
        <TeamSection />
    </div>

    <EventsSection />
    <CreativeSection />
    <AppNews />
</template>

<style lang="scss">
@use './style/general.scss' as *;
@use './style/partials/variables' as *;
@import "@fortawesome/fontawesome-free/css/all.css";

.top-container{
    background-color: $bg_lightgray;
    width: 100%;
    padding-bottom: 1rem;
}

</style>
