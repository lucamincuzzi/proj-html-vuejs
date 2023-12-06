<script>
export default {
    data() {
        return {
            ourProductsImg: ["choco-chip-cookies-600x765.jpg", "strawberry-jam-cookies-600x765.jpg",],
            adHocProducts: [
                {
                    photo: "choco-chip-cookies-400x510.jpg",
                    name: "Choco Chip Cookies",
                    price: "$19.00 - $39.00",
                },
                {
                    photo: "strawberry-jam-cookies-400x510.jpg",
                    name: "Choco Chip Cookies",
                    price: "$24.00 - $62.00",
                },
                {
                    photo: "strawberry-donut-400x510.jpg",
                    name: "Choco Chip Cookies",
                    price: "$24.00 - $42.00",
                },
                {
                    photo: "perfect-macarons-400x510.jpg",
                    name: "Choco Chip Cookies",
                    price: "$18.00 - $52.00",
                }
            ],
            onIt: false,
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
                    <div>
                        <div v-if="onIt"></div>
                        <img v-else src="../assets/images/corporate-bg.jpg" alt="">
                    </div>
                    <div>
                        <div v-if="onIt"></div>
                        <img src="../assets/images/wedding-bg.jpg" alt="">
                    </div>
                </div>
            </div>
        </section>
        <!-- /Corporate & Weddings -->

        <!-- Ad hoc products -->
        <section id="adHocProduct">
            <div class="section wrapper d-flex justify-content-between">
                <div class="description">
                    <h3 class="title">Find a freshly baked product perfect for you</h3>
                    <p class="mt-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. In sed, qui sunt reprehenderit
                        inventore distinctio. Eum, enim! Distinctio blanditiis qui et ducimus temporibus voluptatibus,
                        doloribus
                        laudantium, repellendus alias nemo provident?</p>
                    <button class="btn btn-lg mt-4">Shop All Products</button>
                </div>
                <div class="slider">
                    <Splide :options="{ rewind: true, autoWidth: true, autoHeight: true, perPage: 2, gap: '.5rem' }"
                        aria-label="My Favorite Images">
                        <SplideSlide v-for="product in adHocProducts" class="d-flex flex-column">
                            <!-- Immagine prodotto -->
                            <img :src="getImgPath(product.photo)" alt="">
                            <!-- Descrizione prodotto -->
                            <div class="product-description d-flex flex-column">
                                <!-- Nome prodotto -->
                                <span class="product-name">{{ product.name }}</span>
                                <!-- Prezzo -->
                                <span class="price">{{ product.price }}</span>
                            </div>
                            <!-- /Descrizione prodotto -->
                        </SplideSlide>
                    </Splide>
                </div>
            </div>
        </section>
        <!-- /Ad hoc products -->
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

            .title {
                font-size: 2.5rem;
            }

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

    #adHocProduct {
        .description {
            width: 25%;
            text-align: center;

            .title {
                font-size: 2.5rem;
            }

            p {
                font-size: 1rem;
                opacity: 0.7;
            }

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

        .slider {
            img {
                height: 400px;
            }
            .product-description {
                text-align: center;
                color: $font-main-color;

                .product-name {
                    font-size: 1.5rem;
                    font-family: "", serif;
                    font-weight: bold;
                }
            }
        }
    }
}
</style>