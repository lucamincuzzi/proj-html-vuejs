<script>
export default {
    data() {
        return {
            navLinks: ["Home", "Shop", "About", "Gallery", "Locations", "Journal", "Contact", "My Account"],
            heroSquares: ["Demos", "On Sale"],
        }
    },
}
</script>

<template>
    <header>
        <div class="d-flex justify-content-between align-items-center">
            <!-- Logo -->
            <img src="../assets/images/avada-bakery-logo-retina-200x97.png" alt="hero-img">
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
    <!-- Hero -->
    <!-- Highlight -->
    <div class="hero d-flex justify-content-start">
        <div class="hero-content">
            <span>FRESHY & TASTY BAKERY EVERY DAY</span>
            <h2 class="mt-3">The Perfect Fresh Bread</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo corporis excepturi minima, illo vel suscipit
                soluta pariatur animi nulla eveniet quis rem dignissimos laboriosam? Quidem eaque corrupti porro alias
                sequi!</p>
            <button class="btn btn-lg px-4 mt-4">Explore our products</button>
        </div>
        <div class="square">
            <i class="fa-solid fa-person-chalkboard"></i>
            <span>Demos</span>
        </div>
        <div class="square-1">
            <div class="sale d-flex justify-content-center">
                <span class="dollar" style="color: green">&dollar;</span>
                <span class="sale-price">39</span>
            </div>
            <span>On Sale</span>
        </div>
    </div>
    <!-- /Highlight -->
    <!-- /Hero -->
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

.hero {
    height: 800px;
    background-image: url(../assets/images/hero-header-bakery.jpg);
    background-position: center;
    background-size: cover;
    position: relative;

    .hero-content {
        width: 25%;
        margin: auto 0 auto 100px;

        span {
            font-size: 0.8rem;
        }

        span,
        p {
            opacity: 0.7;
        }

        h2 {
            font-size: 3.5rem;
            font-family: "", serif;
            font-weight: bold;
            color: $font-main-color;
        }

        button {
            font-size: 0.8rem;
            background-color: #ffff;
            color: $font-main-color;

            &:hover {
                background-color: $font-main-color;
                color: #ffff;
            }
        }
    }

    .square,
    .square-1 {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        border-radius: 10px;
        box-shadow: 5px 5px 5px lightgray;
        width: 70px;
        height: 70px;
        position: absolute;
        right: 10px;
        background-color: white;

        span {
            font-size: 0.8rem;
        }
    }

    .square {
        margin-bottom: 10px;
    }

    .square-1 {
        top: 80px;

        .dollar {
            position: absolute;
            left: 14px;
            top: 8px;
        }

        .sale {
            width: 50px;
        }

        span.sale-price {
            font-size: 1.4rem;
            color: green;
        }
    }
}</style>