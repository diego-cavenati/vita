<script>
export default {
    name: 'FooterComponent',
}
</script>

<template>
    <footer>
        <div class="container d-flex">
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
</style>
