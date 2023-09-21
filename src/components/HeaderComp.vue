<template>
    <header class="header">
        <div class="container header__flex">
            <router-link to="/" >
                <img  src="../assets/img/Logo.svg" alt="logo">
            </router-link>
            <NavigationComp  />
        </div>
    </header>
</template>

<script>
import NavigationComp from './NavigationComp.vue';

export default {
    name: 'HeaderComp',
    components: { 
        NavigationComp
    }
};
</script>

<style lang="css" scoped>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
body {
    background: #FFFFFF;
}


a {
    text-decoration: none;
}

.container {
    margin: 0 auto;
    max-width: 1200px;
}

.header {
    margin-top: 44px;
    padding-top: 12.5px;
    padding-bottom: 12.5px;
    margin-bottom: 57px;
}

.header__flex {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>