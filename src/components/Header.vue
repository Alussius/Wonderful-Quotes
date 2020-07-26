<template>
    <div class="row">
        <h3>Quotes Added</h3>
        <div class="progress">
            <div class="progress-bar" role="progressbar" :style="progress()">
                {{ quotes.length }} / {{ maxQuotes }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['maxQuotes', 'quotes'],
    methods: {
        progress() {
            let width = this.quotes.length * 10;
            return "width: " + width + "%";
        }
    }
}
</script>

<style>

</style>