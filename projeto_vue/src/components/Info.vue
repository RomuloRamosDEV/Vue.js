<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Não estou trabalhando no momento.</p>
        <p>Utilizo as seguintes tecnologias para beckend:</p>

        <ul>
            <li v-for="(technology, index) in backend_technologies" v-bind:key="index">
                {{technology}}
            </li>  
        </ul>

        <p>Utilizo as seguintes tecnologias para front-end:</p>

        <ul>
            <li v-for="technology in frontend_technologies" :key="technology.id">
                {{technology.language}}
            </li>  
        </ul>

        <div>
            <button @click="showEmail">{{MostrarEmail}}</button>
        </div>
        <p v-show="email"> Mande um email para {{email}}</p>
        <p>Para acessar meu portfólio <a v-bind:href="meu_link" target="_blank">basta clicar aqui</a></p>

       <Avatar />
    </div>
</template>

<script>

import Avatar from './Avatar.vue';

    export default {
        name: "Info",
    data() {
        return {
            esta_trabalhando: true,
            email: "",
            meu_link: "https://google.com",
            MostrarEmail: 'Mostrar Email',
            backend_technologies: ['JavaScript','PHP','C#'],
            frontend_technologies: [
                {id: 1, language: 'HTML'},
                {id: 2, language: 'CSS'},
                {id: 3, language: 'Vue'},
            ],
        };
    },
    components: { 
        Avatar 
    },
    methods: {
        showEmail() {
            if(this.email == '') {
                this.email = 'romulo@gmail.com';
                this.MostrarEmail = "Esconder Email";
            }else{
                this.email = '';
                this.MostrarEmail = "Mostrar Email";
            }
            
        }
    }

    
}
</script>