<template>
    <h1>Meu Sobrenome é: {{surname}}</h1>
</template>

<script>
    export default {
        name: 'LifeCycle',
        data () {
            return {
                surname: 'Ainda não sei',
            }
        },
        created() {
            setTimeout(() => {
                this.surname = 'Ramos'
            }, 1000);
            
        }
    }
</script>