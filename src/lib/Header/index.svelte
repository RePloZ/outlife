<script lang="ts">
    import { HeaderPosition } from "./type";

    export let selectedPosition : HeaderPosition = HeaderPosition.Home

    const headerPositions = Object.values(HeaderPosition).filter(position => ![HeaderPosition.Home, HeaderPosition.Contact].includes(position))
</script>


<div class="header">
    <p class="header--text">Outside Moovie</p>
    <div class="header--bloc header--bloc__space">
        {#each headerPositions as position}
        <div class="header--box">
            {#if selectedPosition === position }
                <p class="header--text header--text__activate">{position}</p>
            {:else}
                <p class="header--text">{position}</p>
            {/if}
        </div>
        {/each}
    </div>
    <p class="header--text">Contact</p>
</div>

<style lang="scss">
    .header {
        z-index: 2;
        overflow: hidden;
        position: sticky;
        display: flex;
        top: 0;
        left: 0;
        width: 100%;
        background-color: #605D98;
        color: white;
        margin: 0;
        padding: 0;
        justify-content: space-between;

        &--text {
            padding: 0 2rem;

            &__activate {
                border-bottom: 0.5rem white;
            }
        }

        &--bloc {
            display: flex;

            &__space {
                justify-content: space-around;
            }

        }

        &--box {
            display: flex;
        }
    }
</style>