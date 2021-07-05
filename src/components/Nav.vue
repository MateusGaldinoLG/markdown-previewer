<template>
    <div class="nav">
        <img alt="Vue logo" src="../assets/logo.png" class="logo">
        <h1 class="title">Text to markdown converter</h1>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.nav{
    display: flex;
    justify-content: flex-start;
    align-items: center;
    margin-bottom: 10px;
    padding: 0.35em;
    color: hsl(0, 0%, 100%);
    background-color: hsl(153, 49%, 35%);
    .logo{
        width: 40px;
        height: 40px;
        margin: 0 7px;
    }
    .title{
        font-size: 1.5rem;
        font-weight: 600;
    }
}
</style>