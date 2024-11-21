<script>
    export let items;
    export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as tab}
            <li>
                <div class:active={tab === activeItem}>{tab}</div>
            </li>
        {/each}
    </ul>
</div>

<style>

</style>