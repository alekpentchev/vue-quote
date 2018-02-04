<template>
    <div class="col-md-12">
        <h1>Quotes Added</h1>
        <div class="progress">
            <div class="progress-bar" role="progressbar" :style="{width: (quoteAmount/quoteMaxAmount) * 100 + '%'}" :aria-valuenow="quoteAmount" aria-valuemin="0" :aria-valuemax="quoteMaxAmount">{{ quoteAmount }} / {{quoteMaxAmount}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteAmount','quoteMaxAmount']
    }
</script>

<style scoped>

</style>

