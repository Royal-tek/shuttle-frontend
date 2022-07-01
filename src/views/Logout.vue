<template>
    <div class="holder">

    </div>
</template>

<script>
export default {
    name : 'Logout',
    
    methods:{
        logout(){
            this.$router.push('/')
            localStorage.removeItem('auth_token')
            this.$store.state.token = ''
            this.$store.state.isAuthenticated = false
        }
    },
    mounted(){
        this.logout()
    },
}
</script>