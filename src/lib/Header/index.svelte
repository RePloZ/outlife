<script lang="ts">
    import { onMount } from "svelte";
    import { HeaderPosition } from "../type";

    export let selectedPosition : HeaderPosition = HeaderPosition.Home

    const headerPositions = Object.values(HeaderPosition).filter(position => ![HeaderPosition.Home, HeaderPosition.Contact].includes(position))
    $: isInside = headerPositions.includes(selectedPosition)

    let showMobileMenu = false

    const navItems = headerPositions.map((headerPosition, index) => ({ label: headerPosition, href: `#${headerPosition}` }))
    const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);

    const mediaQueryHandler = e => {
    // Reset mobile state
    if (!e.matches) { showMobileMenu = false; }
    };

    // Attach media query listener on mount hook
    onMount(() => {
        const mediaListener = window.matchMedia("(max-width: 767px)");
        mediaListener.addEventListener('change', mediaQueryHandler)
    })
</script>


<div class="header">
    <a href={['#', HeaderPosition.Home].join('')} class="header--text">Watch It Oustide</a>
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

            &__space {
                justify-content: space-around;
            }
        }

        &--box {
            display: flex;
        }
    }
</style>