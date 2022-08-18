<template>
    <div>
        <h2>Meu formulário:</h2>
        <form action="" @submit="enviarFormulario($event)">
            <div>
                <input type="text" v-model="name">
            </div>
            <div>
                <input type="text" v-model="email">
            </div>
            <div>
                <InputText />
            </div>
            <input type="submit">
        </form>
    </div>
</template>

<script>
    import InputText from './form/InputText.vue';
    
    export default {
        name: "Form",
        components: { InputText },
        methods: {
            enviarFormulario(e) {

                e.preventDefault();

                const name = this.name;
                const email = this.email;

                alert('o nome é: ' + name + ' e o email é: ' + email);
            } 
        },
        data () {
            return {
                name: '',
                email: ''
            }
        }
    }
</script>