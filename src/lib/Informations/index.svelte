<div class="informations">
    <h2>Information</h2>
    <div class="informations--circle informations--circle__first">
        <h3>
            5 - 8
            <br>
            August 
        </h3>
    </div>
    <iframe
    class="informations--top"
    style="border:0"
    loading="lazy"
    allowfullscreen
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2948.4536004978845!2d-71.07262194821601!3d42.35417144336258!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89e3709e822b60bb%3A0xcbd77f0b5e16e701!2sPublic%20Garden!5e0!3m2!1sfr!2sfr!4v1618483182295!5m2!1sfr!2sfr"></iframe>
    <div class="informations--circle informations--circle__third">
        <h3>1,500 people</h3>
    </div>
</div>

<style lang="scss">
    .informations {
        padding: 2rem;
        h2 {
            text-align: center;
            padding: 2rem;
        }
        position: relative;
        width: 100vw;
        min-height: 100vmin;
        background: #66648C;

        &--top {
            position: absolute;
            top: 20vmin;
            left: 50%;
            transform: translateX(-50%);
            width: 75%;
            height: 30vmin;
        }

        &--circle {
            position: absolute;
            display: grid;
            place-items: center;

            h3 {
                text-align: center;
            }

            &__first {
                bottom: 10vmin;
                left: 10vmin;
            }
            &__third {
                bottom: 10vmin;
                right: 10vmin;
            }

            width: 30vmin;
            height: 30vmin;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.4);
        }
    }
</style>