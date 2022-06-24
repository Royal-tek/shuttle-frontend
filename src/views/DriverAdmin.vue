<template>
    <div class="holder">
        <Navbar/>
        
        <Footer/>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
import Footer from '../components/Footer.vue'

export default {
    name: "DriverAdmin",
    components: {
    Navbar,
    Footer,
    
}
}
</script>

<style lang="scss" scoped>

</style>