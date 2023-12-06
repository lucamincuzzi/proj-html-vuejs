<script>
export default {
    data() {
        return {
            navLinks: ["Home", "Shop", "About", "Gallery", "Locations", "Journal", "Contact", "My Account"]
        };
    },
}
</script>

<template>
    <header>
        <div class="d-flex justify-content-between align-items-center">
            <!-- Logo -->
            <img src="../assets/images/avada-bakery-logo-retina-200x97.png" alt="">
            <!-- /Logo -->
            <!-- Navbar -->
            <nav class="d-flex aling-items-center">
                <!-- Link -->
                <ul class="d-flex">
                    <li v-for="link in navLinks" class="me-4"><a>{{ link.toUpperCase() }}</a></li>
                </ul>
                <!-- /Link -->
                <!-- Carrello -->
                <i class="fa-solid fa-cart-shopping" style="color: #5b2ca2"></i>
                <!-- /Carrello -->
            </nav>
            <!-- /Navbar -->
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

header {
    background-color: $main-bg-color;

    div {
        width: 95%;
        margin: 0 auto;

        li,
        i {
            cursor: pointer;
        }

        ul {
            list-style-type: none;
            font-size: 0.7rem;
            font-weight: 400;
            color: $font-main-color;

            li {
                position: relative;

                &::after {
                    content: "";
                    position: absolute;
                    left: 0;
                    bottom: -5px;
                    width: 100%;
                    height: 0px;
                    background-color: $font-main-color;
                    transition: all .3s;
                }

                &:hover {
                    &::after {
                        height: 1.5px;
                    }
                }
            }
        }

        a {
            color: inherit;
        }
    }
}
</style>