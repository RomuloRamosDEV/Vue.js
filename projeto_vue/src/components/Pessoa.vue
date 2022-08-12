<template>
    <div>
        <h2>Esta é a descrição da Pessoa: {{nome}}</h2>
        <Info/>
        
    </div>
</template>

<script>

    import Info from './Info';

    export default {
        name: "Pessoa",
        data() {
            return {
                nome: "Romulo",
            };
        },
        components: {
            Info
        }
}   
</script>