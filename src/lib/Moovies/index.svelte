<div class="moovies">
    <h3 class="moovies--text">Let's Watch Moovies Together !</h3>

    <div class="moovies--list">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
        <img src="" alt="" class="moovies--list__affiche">
    </div>
</div>

<style lang="scss">
    .moovies {
        position: relative;
        width: 100vw;
        min-height: 100vh;
        padding: 10vh 0;
        background: linear-gradient(180deg, #2F2E41 0%, #2F2E41 0.01%, #66648C 100%);

        &--list {
            --auto-grid-min-size: 16rem;
            display: grid;
            place-items: center;
            grid-template-columns: repeat(auto-fill, minmax(var(--auto-grid-min-size), 1fr));
            grid-template-rows: 1fr 1fr;
            gap: 10vh 5vw;
            margin: 0 10vw;

            &__affiche {
                width: 147px;
                height: 213px;
            }
        }

        &--text {
            margin: 0;
            padding: 5rem 0;

            color: white;
            text-align: center;
            font-size: 36px;
        }
    }
</style>