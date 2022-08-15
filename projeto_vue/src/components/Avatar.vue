<template>
    <div>
        <img :src="avatar" :alt="descricao">
        <p>tete</p>
    </div>
</template>

<script>
    export default {
        name: "Avatar",
        data() {
            return {
                avatar: "/img/php-image.jpg",
                descricao: 'Avatar'
            }
        }
    }
</script>