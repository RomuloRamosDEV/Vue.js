<template>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Projetos</a></li>
    </ul>
</template>

<script>
    export default {
        name: "Header",
        data() {
            return {

            }
        }
    }
</script>

<style scoped>
    ul{
        list-style: none;
        display: flex;
    }
    li{
        margin-right: 10px;
    }

    a {
        color: white;
    }
</style>