<template>
    <div class="row mb-2">
        <div class="col-sm-12">
            <h2>Quotes:</h2>
            <div class="progress">
                <div 
                class="progress-bar"
                :style="{width: (quoteCount/maxQuotes)*100 + '%'}">
                    {{quoteCount}}/{{maxQuotes}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCount','maxQuotes']
}
</script>
