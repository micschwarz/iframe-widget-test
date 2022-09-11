<script lang="ts">
    import Widget from './lib/Widget.svelte';

    let widgets: string[] = JSON.parse(localStorage.getItem('widgets')) ?? [];

    let widgetContent = '';
    const add = () => {
        widgets = [...widgets, widgetContent];
        widgetContent = '';
        localStorage.setItem('widgets', JSON.stringify(widgets));
    };
</script>

<main class="container py-4">
    <h1>Widgets</h1>

    <div class="my-2">
        <textarea name="src" rows="2" class="form-control w-100 mb-1" bind:value={widgetContent} />
        <button class="btn btn-primary" disabled={!widgetContent.length} on:click={add}>Add</button>
    </div>

    <div class="row g-2">
        {#each widgets as widget (widget)}
            <Widget src={widget} />
        {/each}
    </div>
</main>
