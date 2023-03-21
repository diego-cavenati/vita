<script>
export default {
    name: 'SupportUs',
    data() {
        return {
            isWide: false,
        };
    },
    mounted() {
        this.isWide = window.innerWidth >= 391;
        window.addEventListener('resize', this.onResize);
    },
    beforeUnmount() {
        window.removeEventListener('resize', this.onResize);
    },
    methods: {
        onResize() {
            this.isWide = window.innerWidth >= 391;
        },
    },
}
</script>

<template>
    <div id="support_us">
        <div class="container" :class="{ 'd-flex align-items-center justify-content-between': isWide }">
            <h2 :class="{ 'title_xl': isWide, 'title_m': !isWide }">Il tuo supporto è fondametale</h2>
            <span>
                <a href="#">Dai il tuo contributo</a>
            </span>
        </div>
    </div>
</template>

<style lang="scss">
@use '../styles/general.scss';
@use '../styles/partials/variables.scss' as *;

#support_us {
    padding: 3rem 0;
    background-color: $color-secondary;


}
</style>
