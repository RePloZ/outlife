<script lang="ts">
    import { onMount } from "svelte";
    import { HeaderPosition } from "../type";

    export let selectedPosition : HeaderPosition = HeaderPosition.Home

    const headerPositions = Object.values(HeaderPosition).filter(position => ![HeaderPosition.Home, HeaderPosition.Contact].includes(position))
    let width = 0
    $: isInside = headerPositions.includes(selectedPosition)
    $: documentWidth = width

    let showMobileMenu = false
    let isMobile = false

    const navItems = headerPositions.map(headerPosition => ({
        label: headerPosition,
        href: `#${headerPosition}`
    }))

    const handleMobileIconClick = () => {
        showMobileMenu = !showMobileMenu
        console.log(showMobileMenu)
    }

    const mediaQueryHandler = e => {
        // Reset mobile state
        if (!e.matches) {
            showMobileMenu = false;
            isMobile = false
        } else {
            isMobile = true
        }
    };

    // Attach media query listener on mount hook
    onMount(() => {
        width = document.body.offsetWidth
        if (width < 767) { isMobile = true }
        const mediaListener = window.matchMedia("(max-width: 767px)");
        mediaListener.addEventListener('change', mediaQueryHandler)
    })
</script>


<div class="header">
    {#if (documentWidth > 767)}
    <a href={['#', HeaderPosition.Home].join('')} class="header--text">Watch It Oustide</a>
    {:else}
    <a class="header--text" on:click={handleMobileIconClick}>Menu</a>
    {/if}
    {#if (documentWidth > 767)}
    <div class="header--bloc header--bloc__space">
        {#each navItems as position}
        <div class="header--box">
                <a
                href={position.href}
                class={
                    [
                        "header--text",
                        isInside ? "header--text-active" : "",
                        selectedPosition === position.label
                        ? "header--text__selected"
                        : "",
                    ].join(' ')
                }>{position.label}</a>
        </div>
        {/each}
    </div>
    <a  href={['#', HeaderPosition.Contact].join('')} class="header--text">Contact</a>
    {/if}
</div>
{#if (documentWidth < 767)}
<div class={[
    "header--sidebar",
    showMobileMenu ? "header--sidebar__active" : ""
].join(' ')}>
    <a on:click={handleMobileIconClick} href={['#', HeaderPosition.Home].join('')} class="header--text">Watch It Oustide</a>
    {#each navItems as position}
    <div class="header--box">
            <a
            href={position.href}
            on:click={handleMobileIconClick}
            class={
                [
                    "header--text",
                    isInside ? "header--text-active" : "",
                    selectedPosition === position.label
                    ? "header--text__selected"
                    : "",
                ].join(' ')
            }>{position.label}</a>
    </div>
    {/each}
    <a on:click={handleMobileIconClick} href={['#', HeaderPosition.Contact].join('')} class="header--text">Contact</a>
</div>
{/if}
<style lang="scss">
    .header {
        z-index: 2;
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
            color: hsl(0, 0%, 15%);
            text-decoration: none;
            padding: 1rem;

            &:hover {
                background: hsl(243, 40%, 48%);
                color:white;
                text-decoration:none;
                cursor:pointer;
            }

            &__activate {
                border-bottom: 0.5rem white;
            }
        }

        &--bloc {
            display: flex;
            @media screen and (max-width: 767px) {
                display: none;
            }

            &__space {
                justify-content: space-around;
            }
        }

        &--box {
            display: flex;
        }

        &--sidebar {
            display: none;
            position: fixed;
            top: 50px;
            width: 100vw;
            height: calc(100vh - 50px);
            transition: width ease-in 200ms;

            &__active {
                z-index: 30;
                background: hsla(0, 23%, 88%, 0.81);
                color: white;
                width: 100% !important;
                height: 100%;
                display: grid;
                place-items: center;
                @media screen and (max-width: 767px) {
                    width: 0;
                }
            }

        }
    }
</style>