<template>
    <nav class="nav">
        <ul class="nav__list">
            <li class="navigation__item">
                <router-link to="/" class="nav__link">Home</router-link>
            </li>
            <li class="navigation__item">
                <router-link to="/project" class="nav__link">Project</router-link>
            </li>
            <li class="navigation__item">
                <router-link to="/blog" class="nav__link">Blog</router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'NavigationComp',
};
</script>

<style lang="css" scoped>
ul {
  padding: 0;
  list-style: none;
}
a {
    text-decoration: none;
}
.nav__list {
    display: flex;
    flex-wrap: wrap;
    gap: 50px;
}

.nav__link {
    font-family: Jost;
    font-size: 20px;
    font-weight: 400;
    line-height: 25px;
    letter-spacing: 0em;
    text-align: center;
    color: #292F36;
}
</style>