<script>
export default {
    data() {
        return {
            navLinks: ["Shop", "About", "Gallery", "Locations", "Journal", "Contact", "Orders",],
            socials: ["fa-instagram", "fa-twitter", "fa-facebook-f", "fa-pinterest",],
        };
    },
}
</script>

<template>
    <footer>
        <!-- Footer top -->
        <div class="footer-top cta">
            <div class="wrapper d-flex align-items-center h-100">
                <div class="container">
                    <div class="cta-text">
                        <span>TRY OUR SEASONAL PRODUCTS</span>
                        <h2 class="mt-3">Order for pick-up or delivery to your home</h2>
                        <!-- CTA button -->
                        <button class="btn btn-lg py-3 px-5">Shop Now</button>
                    </div>
                </div>
            </div>
        </div>
        <!-- /Footer top -->
        <!-- Footer bottom -->
        <div class="footer-bottom mt-5">
            <div class="footer-container">
                <!-- Parte superiore -->
                <div class="upper-side d-flex justify-content-between align-items-center">
                    <div class="logo-links">
                        <!-- Logo -->
                        <img src="../assets/images/avada-bakery-logo-retina-200x97.png" alt="">
                        <!-- /Logo -->
                        <!-- Link -->
                        <ul class="d-flex gap-4 mt-4">
                            <li v-for="link in navLinks">
                                <a>{{ link }}</a>
                            </li>
                        </ul>
                        <!-- /Link -->
                    </div>
                    <!-- Form -->
                    <div class="form w-45">
                        <h3 class="cta-form-text mb-5">Subscribe to our Newsletter</h3>
                        <div class="input-group mb-3">
                            <input style="height: 50px" type="text" class="form-control me-4"
                                placeholder="Enter email address*" aria-label="Recipient's username"
                                aria-describedby="basic-addon2">
                            <button class="btn btn-large px-4">Subscribe</button>
                        </div>
                    </div>
                    <!-- /Form -->
                </div>
                <!-- /Parte superiore -->
                <!-- Parte inferiore -->
                <div class="lower-side mt-5 d-flex justify-content-between align-items-center">
                    <!-- /Credits -->
                    <span class="credits"> &copy;Copyright 2012 - 2020 | Avada Theme by ThemeFusion | All Rights Reserved |
                        Powered by Wordpress</span>
                    <!-- /Credits -->
                    <!-- Social -->
                    <ul class="d-flex gap-5">
                        <li v-for="social in socials">
                            <a><i class="fa-brands fa-lg" :class="social"></i></a>
                        </li>
                    </ul>
                    <!-- /Social -->
                </div>
                <!-- /Parte inferiore -->
            </div>
        </div>
        <!-- /Footer bottom -->
    </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

footer {
    .footer-top {
        height: 550px;
        background-image: url(../assets/images/call-to-action-bg.jpg);
        background-position: bottom;
        background-repeat: no-repeat;
        background-size: cover;

        .container {
            margin: auto auto;

            .cta-text {
                width: 65%;
                color: white;

                span {
                    opacity: 0.7;
                }

                h2 {
                    font-size: 4rem;
                    font-family: "", serif;
                    font-weight: bold;
                    margin-bottom: 80px;
                }
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
    }

    .footer-bottom .footer-container {
        width: 90%;
        margin: 0 auto;

        ul {
            list-style-type: none;
            color: $font-main-color;

            a {
                color: inherit;
            }
        }

        .upper-side {

            img {
                position: relative;
                left: 25px;
            }

            li,
            i {
                cursor: pointer;
            }

            .form {

                h3.cta-form-text {
                    text-align: end;
                    font-family: "", serif;
                    font-weight: bold;
                    color: $font-main-color;
                }

                button {
                    font-size: 0.8rem;
                    background-color: $font-main-color;
                    color: #ffff;
                    border-radius: 10px !important;

                    &:hover {
                        background-color: $btn-hover-bg-color;
                        color: $font-main-color;
                    }
                }
            }
        }

        .lower-side {
            span.credits {
                font-size: 0.8rem;
                opacity: 0.7;
            }
        }
    }
}
</style>