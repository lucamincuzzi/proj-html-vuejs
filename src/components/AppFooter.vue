<script>
export default {

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
        <div class="footer-bottom"></div>
        <!-- /Footer bottom -->
    </footer>
</template>

<style lang="scss">
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
}
</style>