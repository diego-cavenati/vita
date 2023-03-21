<script>
export default {
    name: 'ThemesComponent',
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
    <div id="themes">
        <div class="container">
            <h2 :class="{ 'title_xxl': isWide, 'title_xl': !isWide }">Tutti i temi</h2>
            <div class="category">
                <a href="#" class="button tag">ambiente</a>
                <a href="#" class="button tag">economia</a>
                <a href="#" class="button tag">mondo</a>
                <a href="#" class="button tag">non profit</a>
                <a href="#" class="button tag">politica</a>
                <a href="#" class="button tag">società</a>
                <a href="#" class="button tag">welfare</a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss';
@use '../styles/partials/variables.scss' as *;

#themes {
    padding: 4rem 0;
    background-color: $color-background;

    .container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .category {
        display: flex;
    }

    .category .button {
        margin-right: 0.5rem;
    }

    .category .button:last-child {
        margin-right: 0;
    }
}

/**********************
      Responsive
***********************/
@media screen and (max-width: 390px) {
    #themes {
        padding: 2rem 0;
        background-color: $color-background;

        .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .title_xl {
            flex: 1 0 100%;
            margin-bottom: 1rem;
        }

        .category {
            display: flex;
            justify-content: flex-start;
            flex-wrap: wrap;
            margin-left: auto;
        }

        .category .button {
            margin-right: 0.5rem;
            margin-bottom: 0.5rem;
        }

        .category .button:last-child {
            margin-right: 0;
        }
    }
}
</style>
