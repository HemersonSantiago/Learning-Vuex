<template>
    <div>
        <p>Email: {{ email  }}</p>
        <p>Localidade: {{ localidade }}</p>
        <meuButton></meuButton>
    </div>
</template>

<script>

import meuButton from '../shared/button.vue';

export default {  
    components: {
        meuButton,
    },
    computed: {
        email () {
            return this.$store.state.user.email;
        },
        localidade () {
            return this.$store.getters.localidade;
        }
    }
}
</script>

