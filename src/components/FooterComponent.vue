<script>
export default {
    name: 'FooterComponent',
    data() {
        return {
            isWide: false,
        };
    },
    mounted() {
        this.isWide = window.innerWidth >= 390;
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
    <footer>
        <div class="container" :class="{ 'd-flex': isWide }">
            <div class="links">
                <ul>
                    <li><a href="#">Il Gruppo</a></li>
                    <li><a href="#">Note Legali</a></li>
                    <li><a href="#">Chi Siamo</a></li>
                    <li><a href="#">Condizioni d'uso</a></li>
                    <li><a href="#">Privacy</a></li>
                    <li><a href="#">Scrivici</a></li>
                    <li><a href="#">Pubblicità</a></li>
                </ul>
            </div>
            <div class="copyright">
                &copy; 1994-2022 Vita Società Editoriale S.p.A.
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
@use '../styles/general.scss';
@use '../styles/partials/variables.scss' as *;


footer {
    padding: 3rem 0;

    ul {
        display: flex;

        li {
            padding-right: 1.5rem;
        }
    }

    .copyright {
        margin-left: auto;
    }

}

/**********************
      Responsive
***********************/
@media screen and (max-width: 390px) {
    footer {
        padding: 3rem 0;

        ul {
            display: block;

            li {
                padding-right: 0;
                padding-bottom: 1rem;
                font-family: $font-primary;
                font-size: 16px;
                font-weight: 700;
                line-height: 24px;
                letter-spacing: 0em;
                text-align: left;

                &:not(:last-child) {
                    padding-bottom: 1rem;
                }
            }


        }

        .copyright {
            margin-right: auto;
        }

    }
}
</style>
