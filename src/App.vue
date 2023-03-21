<script>
import BlogComponent from './components/BlogComponent.vue';
import CitationComponent from './components/CitationComponent.vue';
import ClaimComponent from './components/ClaimComponent.vue';
import ClosingNews from './components/ClosingNews.vue';
import FooterComponent from './components/FooterComponent.vue';
import MainNews from './components/MainNews.vue';
import NavbarComponent from './components/NavbarComponent.vue';
import SecondaryNews from './components/SecondaryNews.vue';
import ThemesComponent from './components/ThemesComponent.vue';
import ThirdNews from './components/ThirdNews.vue';

export default {
    components: {
        NavbarComponent,
        ThemesComponent,
        MainNews,
        ClaimComponent,
        SecondaryNews,
        CitationComponent,
        BlogComponent,
        ThirdNews,
        ClosingNews,
        FooterComponent
    }
}
</script>

<template>
    <NavbarComponent />
    <ThemesComponent />
    <MainNews />
    <ClaimComponent />
    <SecondaryNews />
    <CitationComponent />
    <BlogComponent />
    <ThirdNews />
    <ClosingNews />
    <FooterComponent />
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
