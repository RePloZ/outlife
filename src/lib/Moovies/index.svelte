<script lang="ts">
    import { HeaderPosition } from "../type";
</script>

<div id={HeaderPosition.Moovies} class="moovies">
    <h3 class="moovies--text">Let's Watch Moovies Together !</h3>

    <div class="moovies--list">
        <img
            src="https://images-na.ssl-images-amazon.com/images/I/81O8AZ%2B4XPL._AC_SY879_.jpg"
            alt=""
            class="moovies--list__affiche"/>
        <img
            src="https://i.pinimg.com/originals/27/1d/1e/271d1e11f9a6bb766f77b9db427c2080.jpg"
            alt="Blindspot"
            class="moovies--list__affiche"/>
        <img
            src="https://i.pinimg.com/236x/c5/41/e8/c541e8b18d1b97837a3dd60b884ab574.jpg"
            alt="Looper"
            class="moovies--list__affiche"/>
        <img
            src="https://i.pinimg.com/236x/cd/d5/9c/cdd59cb10ce0588488ca2c8b0548067a.jpg"
            alt="Her"
            class="moovies--list__affiche"/>
        <img
            src="https://i2.wp.com/www.impawards.com/2009/posters/orphan_ver2_xlg.jpg"
            alt="Orphan"
            class="moovies--list__affiche" />
        <img
            src="https://images.affiches-et-posters.com//albums/3/45877/medium/movie-poster-die-hard-piege-cristal--128435.jpg"
            alt="Die Hard"
            class="moovies--list__affiche"/>
        <img
            src="https://i.ebayimg.com/images/g/yokAAOSw8w1YARbm/s-l1600.jpg"
            alt="The Dark Knight"
            class="moovies--list__affiche"/>
        <img
            src="https://assets.mubicdn.net/images/notebook/post_images/19593/images-w1400.jpg?1443151342"
            alt="The Assassin"
            class="moovies--list__affiche"/>
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
            font-size: 3rem;
        }
    }
</style>