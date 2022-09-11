<script lang="ts">
    export let src: string;
</script>

<div class="col-12 col-md-4 col-xl-3">
    <div class="card">
        <div class="card-body p-0">
            <iframe title="Widget" class="h-100 w-100" srcdoc={src} />
        </div>
    </div>
</div>

<style>
    .card {
        height: 10rem;
    }
</style>
