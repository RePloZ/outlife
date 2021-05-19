<script lang="ts">
    import { HeaderPosition } from "../type";
</script>

<div id={HeaderPosition.Contact} class="contact">
    <h3>SE RENSEIGNER</h3>
    <div class="contact--bloc">
        <div>
            <p>Latest News :</p>
            <a href="https://www.boston.gov/news">
                <img class="contact--image" src="https://patterns.boston.gov/images/public/logo.svg?qrl9xp" alt="City of Boston">
            </a>
        </div>
        <div>
            <p>Boston Public Garden :</p>
            <a href="https://www.boston.gov/parks/public-garden">
                <img class="contact--image" src="https://patterns.boston.gov/images/public/logo.svg?qrl9xp" alt="City of Boston">
            </a>
        </div>
        <div>
            <p>Our social networks</p>
            <div class="contact--line">
                <a href="https://twitter.com/">
                    <img class="contact--icon" src="https://img.icons8.com/android/24/000000/twitter.png"/>
                </a>
                <a href="https://www.facebook.com/">
                    <img class="contact--icon" src="https://img.icons8.com/android/50/000000/facebook-new.png"/>
                </a>
                <a href="https://www.instagram.com/">
                    <img class="contact--icon" src="https://img.icons8.com/metro/26/000000/instagram-new.png"/>
                </a>
            </div>
        </div>
    </div>
</div>

<style lang="scss">
    .contact {
        display: grid;
        place-items: center;
        background-color: #9D9AD9;

        h3 {
            text-align: center;
            color: black;
        }

        &--line {
            display: flex;
            justify-content: space-evenly;
            width: 100%;
        }
        &--bloc {
            display: flex;
            justify-content: space-evenly;
            width: 100%;
            @media screen and (max-width: 767px) {
                flex-direction: column;
                align-items: center;
            }

            div {
                text-align: center;
            }

        }

        &--icon {
            width: 24px;
        }
        &--image {
            width: 10vw;
            max-width: 200px;
        }
    }
</style>