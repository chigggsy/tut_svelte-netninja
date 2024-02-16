<script>
    export let isPromo = false;
    export let showModal = false;
</script>

{#if showModal}
    <div class="backdrop" on:click|self on:keydown>
        <div class="modal" class:promo={isPromo}>
            <slot />
        </div>
    </div>
{/if}

<style>
    .backdrop {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
        position: absolute;
        background-color: hsla(0, 0%, 0%, 0.5);
    }

    .modal {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap: 2rem;
        padding: 5rem;
        background: white;
        color: black;
        border-radius: 0.75rem;
    }

    .promo {
        background: cornflowerblue;
        color: white;
    }
</style>
