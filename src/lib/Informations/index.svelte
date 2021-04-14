<div class="informations">
    <img src="" alt="" class="informations--circle">
    <img src="" alt="" class="informations--circle">
    <img src="" alt="" class="informations--circle">
</div>

<style lang="scss">
    .informations {
        position: relative;
        width: 100vw;
        height: 100vh;
        background: #66648C;

        &--circle {
            position: absolute;

            bottom: 10%;

            &:first {
                top: 10%;
                left: 50%;
                transform: translateX(-50%);
            }

            &:last-child {
                left: 50%;
                transform: translateX(-50%);
            }

            width: 30vmin;
            height: 30vmin;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.4);
        }
    }
</style>