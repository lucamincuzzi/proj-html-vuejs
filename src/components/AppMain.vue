<script>
export default {
    data() {
        return {
            ourProductsImg: ["choco-chip-cookies-600x765.jpg", "strawberry-jam-cookies-600x765.jpg",],
        };
    },
    methods: {
        getImgPath(img) {
            return new URL(`../assets/images/${img}`, import.meta.url).href;
        },
    },
}
</script>

<template>
    <main>
        <!-- Our products -->
        <section id="our-products">
            <div class="section-wrapper d-flex justify-content-between">
                <div class="description">
                    <span class="small-text">OUR PRODUCTS</span>
                    <h3 class="title my-4">All our delectable pastries are baked fresh in our Kitchen every morning, and are
                        made with all-natural,
                        all
                        organic ingredients.</h3>
                    <button class="btn">Start Shopping</button>
                </div>
                <div class="slider">
                    <Splide :options="{ rewind: true, autoWidth: true, autoHeight: true, perPage: 2, gap: '.5rem' }"
                        aria-label="My Favorite Images">
                        <SplideSlide v-for="img in ourProductsImg">
                            <img :src="getImgPath(img)" alt="">
                        </SplideSlide>
                    </Splide>
                </div>
            </div>
        </section>
        <!-- /Our products -->

        <!-- Corporate & Weddings -->
        <section id="corp-wedding">
            <div class="section-text">
                <span class="small-text">CORPORATE & WEDDINGS</span>
                <h3 class="title my-4">Baking Special Moments</h3>
                <div class="photo-container d-flex justify-content-between gap-5">
                    <img src="../assets/images/corporate-bg.jpg" alt="">
                    <img src="../assets/images/wedding-bg.jpg" alt="">
                </div>
            </div>
        </section>
        <!-- /Corporate & Weddings -->
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

main {
    width: 90%;
    margin: 0 auto;

    section {
        margin-bottom: 200px;
    }

    .title {
        font-weight: bold;
        font-family: "", serif;
        color: $font-main-color;
    }

    span.small-text {
        font-size: 0.8rem;
        opacity: 0.7;
    }

    #our-products {
        .description {
            width: 30%;

            button {
                font-size: 0.8rem;
                background-color: $font-main-color;
                color: #ffff;

                &:hover {
                    background-color: $btn-hover-bg-color;
                    color: $font-main-color;
                }
            }
        }
    }

    #corp-wedding {
        .section-text {
            text-align: center;
        }

        img {
            max-width: 920px;
        }

        .photo-container {
            margin-top: 80px;
        }
    }
}
</style>