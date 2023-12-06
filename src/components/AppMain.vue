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
                    name: "Stawberry Jam Cookies",
                    price: "$24.00 - $62.00",
                },
                {
                    photo: "strawberry-donut-400x510.jpg",
                    name: "Strawberry Donut",
                    price: "$24.00 - $42.00",
                },
                {
                    photo: "perfect-macarons-400x510.jpg",
                    name: "Perfect Macarons",
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

        <!-- Bakery process -->
        <section id="bakeryProcess">
            <div class="wrapper d-flex flex-column gap-5">
                <!-- Step uno -->
                <div class="step step-one step-lg">
                    <div class="step-info d-flex flex-column justify-content-between">
                        <div class="step-head d-flex justify-content-between align-items-center">
                            <h2>Tell us what you have in mind</h2>
                            <div class="step-number">01</div>
                        </div>
                        <div class="step-description w-50 align-self-end text-start">
                            <div class="subtitle text-start mb-3"><span>MANUAL INGREDIENTS SELECTION</span></div>
                            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Exercitationem dolorum nesciunt
                                voluptas ex culpa autem. Necessitatibus ipsum quod ea aliquam doloremque, deleniti soluta
                                perferendis assumenda eum ad ullam numquam cupiditate.</p>
                        </div>
                    </div>
                </div>
                <!-- /Step uno -->
                <!-- Step due -->
                <div class="step step-two d-flex gap-3">
                    <div class="step step-m w-50">
                        <div class="step-info d-flex flex-column justify-content-between">
                            <div class="step-head d-flex justify-content-between align-items-center">
                                <h2>We Start Baking</h2>
                                <div class="step-number">02</div>
                            </div>
                            <div class="step-description w-50 align-self-start text-start">
                                <div class="subtitle text-start mb-3"><span>SWEET & DELICIOUS</span></div>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Exercitationem dolorum nesciunt
                                    voluptas ex culpa autem. Necessitatibus ipsum quod ea aliquam doloremque, deleniti
                                    soluta
                                    perferendis assumenda eum ad ullam numquam cupiditate.</p>
                            </div>
                        </div>
                    </div>
                    <div class="quote w-50">
                        <div class="quote-container">
                            <span class="small-text">
                                DON'T JUST TAKE OUR WORD FOR IT
                            </span>
                            <p>"Finally found an alternative to the mass produced products.
                                Something that incorporates real organic ingredients, nutrient dense wellness while
                                promoting sustainability and activity."</p>
                            <span class="small-text quoted">Rachel Cooper, Founder</span>
                        </div>
                    </div>
                </div>
                <!-- /Step due -->
                <!-- Step tre -->
                <div class="step step-three step-lg">
                    <div class="step-info d-flex flex-column justify-content-between">
                        <div class="step-head d-flex justify-content-between align-items-center">
                            <h2>Delivered to your home</h2>
                            <div class="step-number">03</div>
                        </div>
                        <div class="step-description w-50 align-self-start text-start">
                            <div class="subtitle text-start mb-3"><span>BAKED TO ORDER & GIFT WRAPPED</span></div>
                            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Exercitationem dolorum nesciunt
                                voluptas ex culpa autem. Necessitatibus ipsum quod ea aliquam doloremque, deleniti soluta
                                perferendis assumenda eum ad ullam numquam cupiditate.</p>
                        </div>
                    </div>
                </div>
                <!-- /Step tre -->
            </div>
        </section>
        <!-- /Bakery process -->
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

    #bakeryProcess {


        .step,
        .step-m,
        .quote {
            position: relative;
            height: 1000px;
            background-position: center;
            background-size: cover;
        }

        .step-info {
            width: 85%;
            height: 80%;
            margin: 50px auto;

            .step-head {
                h2 {
                    font-family: "", serif;
                    font-size: 4rem;
                    font-weight: bold;
                    color: white;
                }

                .step-number {
                    font-size: 100px;
                    font-weight: 200;
                    letter-spacing: 5px;
                    color: white;
                }
            }

            .step-description {
                color: white;

                .subtitle {
                    opacity: 0.7;
                }
            }
        }

        .step-one {
            background: linear-gradient(rgba(0, 0, 0, 0.2),
                    rgba(0, 0, 0, 0.5)), url(../assets/images/bakery-process-1.jpg);
        }

        .step-two .step-m {
            background: linear-gradient(rgba(0, 0, 0, 0.2),
                    rgba(0, 0, 0, 0.5)), url(../assets/images/bakery-process-2.jpg);
        }

        .step-two {
            .quote {
                background-color: $main-bg-color;

                .quote-container {
                    width: 85%;
                    margin: 150px auto;

                    
                .small-text {
                    font-size: 0.8rem;
                    opacity: 0.7;
                }

                p {
                    font-size: 3.5rem;
                    font-family: "", serif;
                    font-weight: bold;
                    letter-spacing: -1px;
                    color: $font-main-color;
                }
                }

            }
        }

        .step-three {
            background: linear-gradient(rgba(0, 0, 0, 0.2),
                    rgba(0, 0, 0, 0.5)), url(../assets/images/bakery-process-3.jpg);
        }
    }
}
</style>