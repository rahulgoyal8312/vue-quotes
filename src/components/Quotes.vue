<template>
    <div class="col-sm-6 offset-sm-3 col-md-4 offset-md-0 mb-2">
        <div class="card">
            <div class="card-body quote">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.card-body{
    font-size: 24px;
    color: #6e6e6e;
}
.quote{
    cursor: pointer;
}
.quote:hover{
    background-color: #ffe2e2;
}
</style>
