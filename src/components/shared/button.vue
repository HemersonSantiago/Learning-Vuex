<template>
    <div>
        <button :disabled="hasUser" @click="mudarDados">Mudar dados do usuário</button>
    </div>
</template>
<script>

import { mapActions } from 'vuex';

export default {
    methods: {
        mudarDados () {
            const payload = {
                name: 'Teste',
                email: 'teste@teste.com',
                level: 'usuario-teste',
                city: 'itapevi',
                state: 'São Paulo'
            }

            this.changeUser(payload);
        },
        ...mapActions(['changeUser'])
    },
    computed: {
        hasUser () {
            return this.$store.state.user.name === '';
        }
    }
}
</script>
