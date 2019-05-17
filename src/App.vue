<template>
    <div>
      <h1>Usuário</h1>
      <h4>{{ user }}</h4>
      <users></users>
    </div>
</template>


<script>

import Users from './components/users/main.vue';
import { mapState, mapActions } from 'vuex';

export default {
  name: 'App-Vue',
  mounted() {
    const payload = {
      name: 'Hemerson',
      email: 'hemerson_rdg@hotmail.com',
      level: 'admin',
      city: 'Barueri',
      state: 'São Paulo'
    }
    setTimeout(() => {
      this.changeUser(payload);
    }, 3000)
  },
  components: {
    Users,
  },
  computed: { 
    ...mapState({
      user: state =>  {
        const { name, email } = state.user;
        return `O usuário logado possui o nome ${name} e o email ${email}`;

      }

    })
  },
  methods: {
    ...mapActions(['changeUser'])
  }
}
</script>

<style>

</style>
