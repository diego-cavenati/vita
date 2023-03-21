<script>
export default {
    name: 'MainNews',
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
    <div id="main_news">
        <div class="principal">
            <div class="container">
                <div class="news_info">
                    <div class="button tag">Migranti</div>
                    <div :class="{ 'title_xl': isWide, 'title_m': !isWide }">Roccella Jonica, la Lampedusa che l'Italia
                        ignora</div>
                    <div class="author_info">
                        <img class="author_image" src="../assets/img/author_1.jpg" alt="Autore" />
                        <div class="author_text">
                            <div class="author_name">Di Alessandro Puglia</div>
                            <div class="title_xs">29 Giugno 2022</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@use '../styles/general.scss';
@use '../styles/partials/variables.scss' as *;

#main_news {
    width: 100%;
    color: $color-primary-light;
    z-index: 1;

    .principal {
        background-image: url('../assets/img/lampedusa.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        height: 30rem;
        width: 100%;
        position: relative;
    }

    .principal::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.5);
        z-index: 5;
    }

    .button {
        width: 78px;
        padding: 0.4rem 0.7rem;
        margin-bottom: 1.5rem;
    }

    .news_info {
        z-index: 10;
        padding-top: 13rem;
        position: relative;
    }

    .author_info {
        display: flex;
        align-items: center;
    }

    .author_image {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        margin-right: 10px;
    }

    .title_xl {
        max-width: 50%;
        padding-bottom: 1.5rem;
    }
}


/**********************
      Responsive
***********************/
@media screen and (max-width: 390px) {
    #main_news {

        .principal {
            height: 20rem;
        }

        .button {
            margin-bottom: 1rem;
        }

        .news_info {
            padding-top: 6rem;
        }

        .title_m {
            max-width: 70%;
            padding-bottom: 1rem;
        }
    }
}
</style>
