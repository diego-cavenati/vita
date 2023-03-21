<script>
export default {
    name: 'NavbarComponent',
    data() {
        return {
            isOpen: false,
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
        toggleMenu() {
            this.isOpen = !this.isOpen;
        },
    },
}
</script>

<template>
    <nav>
        <div :class="{ 'container': isWide }">
            <!-- top section of navbar -->
            <div class="top_section">
                <div class="links">
                    <ul>
                        <li><a href="#">Contribuisci</a></li>
                        <li><a href="#">Abbonati</a></li>
                    </ul>
                </div>
                <div class="login">
                    <svg preserveAspectRatio="none" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg"
                        v-bind="$props">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M14.4303 6.70213C14.4303 8.74866 13.4162 10.5493 11.8845 11.5771C12.4389 11.7767 12.9759 12.0327 13.4874 12.3429C14.8758 13.1846 16.0282 14.395 16.8292 15.852C17.0154 16.1908 16.9063 16.6256 16.5799 16.8235C16.251 17.0228 15.8324 16.9027 15.645 16.5619C14.9631 15.3213 13.9823 14.2916 12.8018 13.5758C11.6213 12.8601 10.2824 12.4843 8.91984 12.4843C7.55724 12.4843 6.21854 12.8601 5.03808 13.5758C3.85756 14.2916 2.87682 15.3213 2.19483 16.5619C2.00745 16.9027 1.58886 17.0228 1.26002 16.8235C0.933613 16.6256 0.824462 16.1908 1.0107 15.852C1.81166 14.395 2.96405 13.1846 4.35242 12.3429C4.86397 12.0327 5.40087 11.7768 5.95521 11.5772C4.42349 10.5494 3.40933 8.74868 3.40933 6.70213C3.40933 3.51243 5.87287 0.919995 8.91984 0.919995C11.9668 0.919995 14.4303 3.51243 14.4303 6.70213ZM4.7747 6.70213C4.7747 4.29247 6.63414 2.34573 8.91984 2.34573C11.2055 2.34573 13.065 4.29247 13.065 6.70213C13.065 9.11179 11.2055 11.0585 8.91984 11.0585C6.63414 11.0585 4.7747 9.11179 4.7747 6.70213Z"
                            fill="black" />
                    </svg>
                    Accedi
                </div>
            </div>

        </div>


        <!-- bottom section navbar -->
        <div class="nav_action">

            <!-- hamburghr menu -->
            <div class="box_action">
                <div class="hamburger_menu" :class="{ active: isOpen }" @click="toggleMenu">
                    <span class="hamburger_line"></span>
                    <span class="hamburger_line"></span>
                    <span class="hamburger_line"></span>
                </div>
            </div>

            <!-- search -->
            <div class="box_action">
                <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                        d="M8.84614 1.53846C4.81022 1.53846 1.53846 4.81022 1.53846 8.84614C1.53846 12.8821 4.81022 16.1538 8.84614 16.1538C12.8821 16.1538 16.1538 12.8821 16.1538 8.84614C16.1538 4.81022 12.8821 1.53846 8.84614 1.53846ZM0 8.84614C0 3.96055 3.96055 0 8.84614 0C13.7317 0 17.6923 3.96055 17.6923 8.84614C17.6923 13.7317 13.7317 17.6923 8.84614 17.6923C3.96055 17.6923 0 13.7317 0 8.84614Z"
                        fill="#E63036" />
                    <path fill-rule="evenodd" clip-rule="evenodd"
                        d="M14.0136 14.0138C14.314 13.7134 14.801 13.7134 15.1014 14.0138L19.7745 18.6868C20.0749 18.9872 20.0749 19.4743 19.7745 19.7747C19.4741 20.0751 18.9871 20.0751 18.6867 19.7747L14.0136 15.1016C13.7132 14.8012 13.7132 14.3142 14.0136 14.0138Z"
                        fill="#E63036" />
                </svg>
            </div>

        </div>
    </nav>
</template>

<style lang="scss">
@use '../styles/general.scss';
@use '../styles/partials/variables.scss' as *;

nav {

    .top_section {
        padding: 0.7rem 0;
        display: flex;
        align-items: center;

        .links {

            ul {
                display: flex;
                align-items: center;
                margin-bottom: 0;

                li {
                    padding-right: 1.5rem;
                }
            }
        }

        .login {
            margin-left: auto;

            svg {
                width: 1rem;
                margin-right: 0.5rem;
            }
        }
    }

    .nav_action {
        display: flex;
        border-top: 1px solid black;
        border-bottom: 1px solid black;

        // box structure
        .box_action {
            padding: 2.37rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .box_action:first-child {
            border-right: 1px solid black;
            margin-right: auto;

        }

        .box_action:last-child {
            border-left: 1px solid black;
            margin-left: auto;
        }

        // hamburgher menu
        .hamburger_menu {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 20px;
            cursor: pointer;
            transition: transform 0.3s ease-in-out;
        }

        .hamburger_line {
            width: 20px;
            height: 2px;
            border-radius: 1rem;
            background-color: $color-primary;
            transition: transform 0.3s ease-in-out, opacity 0.2s ease-in-out;
        }

        .hamburger_menu.active .hamburger_line:nth-child(1) {
            transform: translateY(9px) rotate(45deg);
        }

        .hamburger_menu.active .hamburger_line:nth-child(2) {
            opacity: 0;
        }

        .hamburger_menu.active .hamburger_line:nth-child(3) {
            transform: translateY(-8px) rotate(-45deg);
        }
    }
}


/**********************
      Responsive
***********************/
@media screen and (max-width: 390px) {
    nav {
        .top_section {
            margin-top: 3rem;
            padding: 0;

            .links {
                width: 100%;

                ul {
                    border-top: 1px solid black;
                }

                li {
                    border-right: 1px solid black;
                    padding: 1rem;
                    flex-basis: 50%;
                    display: flex;
                    align-items: center;
                    justify-content: center;

                    &:last-child {
                        border-right: 0;
                    }
                }
            }

            .login {
                display: none;
            }
        }


        .nav_action {

            .box_action {
                padding: 1rem;
            }
        }
    }
}
</style>
