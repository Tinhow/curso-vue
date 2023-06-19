<template>
    <div class="header">
        <header>
            <h1>{{ title }}</h1>
        </header>
    </div>
    
</template>

<script>

    export default {
        name: 'TheHeader',
        data() {
            return {
                title: 'Hello World'
            }
        }
    }

</script>


<style>

    body {
        margin: 0;
        padding: 0;
    }

    .header {
        background-color: #000;
        color: #fff;
        padding: 20px;
        text-align: center;
        width: 100%;
    }
</style>