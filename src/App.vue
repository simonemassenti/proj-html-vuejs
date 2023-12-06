<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';
import AppSpecialties from './components/AppSpecialties.vue';
import EventsSection from './components/EventsSection.vue';
import TeamSection from './components/TeamSection.vue';
import CreativeSection from './components/CreativeSection.vue';
import AppNews from './components/AppNews.vue';
import AppTestimonials from './components/AppTestimonials.vue';
import AppVideo from './components/AppVideo.vue';
import ContactUs from './components/ContactUs.vue';
import AppClients from './components/AppClients.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    components: {
    AppHeader,
    AppHero,
    AppSpecialties,
    TeamSection,
    EventsSection,
    CreativeSection,
    AppNews,
    AppTestimonials,
    AppVideo,
    ContactUs,
    AppClients,
    AppFooter
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
    <AppTestimonials />
    <AppVideo />
    <ContactUs />
    <AppClients />
    <AppFooter />
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
