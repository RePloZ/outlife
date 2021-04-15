<script lang="ts">
    const handleClick = (event) => {
        event.preventDefault();
    }
</script>

<div class="booking">
    <div class="booking--box">
        <div class="booking--text">
            <h3>Book your place</h3>
            <p>Come live an unique experience</p>
            <p>Number of place limited !</p>
        </div>
        <form class="booking--form">
            <div class="inline">
                <input class="booking--form__input" type="text" placeholder="First Name">
                <input class="booking--form__input" type="text" placeholder="Last Name">
            </div>
            <input class="booking--form__input booking--form__large" type="text" placeholder="Email">
            <button class="booking--form__button" on:click={handleClick}>
                <p>
                    <span class="bg" />
                    <span class="base" />
                    <span class="text">Reserve</span>
                </p>
            </button>
        </form>
    </div>
</div>

<style lang="scss">
    $base: #0f1923;
    $white: #ece8e1;
    $pink: #2F2E41;
    $height: 54px;
    $transition: 0.3s ease-out all;
    .inline {
        display: flex;
        align-items: center;
        flex-basis: 2rem;

        input {
            margin: 2rem;
        }
    }

    .booking {
        display: grid;
        place-items: center;
        width: 100%;
        height: 50vh;
        background-color: #2d2c3b;

        &--box {
            display: flex;
            background-color: #110e44a4;

        }

        &--text {
            background-color: #2f2e4157;
            color: white;
            padding: 2rem;

        }

        &--form {
            padding: 2rem;
            display: grid;
            place-items: center;
            grid-column-gap: 2rem;

            &__large {
                margin: 2rem;
                margin-top: 0;
            }

            &__input {
                box-sizing: border-box;
                display: block;
                width: 80%;
                border: 3px solid black;
                padding: calc(0.5rem * 1.5) 0.5rem;
                color: white;
                background: transparent;
                border-radius: 4px;

                &:focus {
                    border-color: #2F2E41;
                    transition: all 0.2s ease-in;
                }
            }

            &__button {
                background: none;
	            border: none;
	            font: inherit;
	            cursor: pointer;
	            outline: inherit;
                width: 100%;
                max-width: 10rem;
                min-width: 2rem;
                height: $height;
                padding: 8px;
                font-size: 0.8rem;
                font-weight: 900;
                color: $white;
                text-align: center;
                text-transform: uppercase;
                text-decoration: none;
                box-shadow: 0 0 0 1px inset rgba($white, 0.3);
                position: relative;
                margin: 10px 0;

                &.transparent:hover > p {
                  color: $white;
                  & span.text {
                    box-shadow: 0 0 0 1px $white;
                  }
                }
                &.transparent > p {
                  background: $base;
                  color: $white;
                  & span.base {
                    border: 1px solid $white;
                  }
                }

                & p {
                  margin: 0;
                  height: $height;
                  line-height: $height;
                  box-sizing: border-box;
                  z-index: 1;
                  left: 0;
                  width: 100%;
                  position: relative;
                  overflow: hidden;
                  & span.base {
                    box-sizing: border-box;
                    position: absolute;
                    z-index: 2;
                    width: 100%;
                    height: 75%;
                    left: 0;
                    border: 1px solid $pink;
                  }
                  & span.bg {
                    left: -5%;
                    position: absolute;
                    background: $pink;
                    width: 0;
                    height: 75%;
                    z-index: 3;
                    transition: $transition;
                    transform: skewX(-10deg);
                  }
                  & span.text {
                    z-index: 4;
                    width: 100%;
                    transform: translateY(-10%);
                    position: absolute;
                    left: 0;
                    top: 0;
                    }
                }
                &:hover {
                  color: $white;
                  & span.bg {
                    width: 110%;
                  }
                  & span.text:after {
                    background: $white;
                  }
                }
            }
        }
    }
</style>