<template>
    <footer class="footer">
        <div class="container footer__flex">
            <div class="footer__interno">
                <img class="footer__interno_img" src="../assets/img/Logo.svg" alt="logo">
                <p class="footer__interno_text">It is a long established fact that a reader will be distracted lookings.</p>
                <div class="footer__interno_seti">
                    <a href="упс пути нет">
                        <img src="../assets/img/twit.svg" alt="twit">
                    </a>
                    <a href="упс пути нет">
                        <img src="../assets/img/in.svg" alt="in">
                    </a>
                </div>
            </div>
            <div class="footer__pages">
                <h3 class="footer__pages_heading">Pages</h3>
                <NavigationComp class="navigation" />
            </div>
            <div class="footer__contact">
                <h3 class="footer__contact_heading">Contact</h3>
                <p class="footer__contact_text">55 East Birchwood Ave. Brooklyn, New York 11201</p>
                <p class="footer__contact_text">contact@interno.com</p>
                <p class="footer__contact_telephon">(123) 456 - 7890</p>
            </div>
        </div>
    </footer>
</template>

<script>
import NavigationComp from './NavigationComp.vue';

export default {
    name: 'FooterComp',

    components: {
        NavigationComp
    }
};
</script>

<style>

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


/*footer*/

.footer {
    height: 272px;
    margin-bottom: 134px;
}

.footer__flex {
    display: flex;
}

.footer__interno {
    width: 393px;
}

.footer__interno_img{
    margin-bottom: 18px;
}

.footer__interno_text {
    margin-bottom: 31px;
    font-family: Jost;
    font-size: 22px;
    font-weight: 400;
    line-height: 33px;
    letter-spacing: 0.01em;
    text-align: left;
    color: #4D5053;
}

.footer__interno_seti {
    display: flex;
    flex-wrap: wrap;
    gap: 54px;
}

.footer__pages {
    width: 125px;
    margin-left: 101px;
}

.footer__pages_heading {
    font-family: DM Serif Display;
    font-size: 25px;
    font-weight: 400;
    line-height: 31px;
    letter-spacing: 0em;
    text-align: left;
    color: #292F36;
    margin-bottom: 9px;
}

.footer__pages_nav {
    width: 72px;
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
}

.footer__pages_text {
    font-family: Jost;
    font-size: 22px;
    font-weight: 400;
    line-height: 66px;
    letter-spacing: 0.01em;
    text-align: left;
    color: #4D5053;
}

.footer__contact {
    width: 258px;
    margin-left: 322px;
}

.footer__contact_heading {
    margin-bottom: 26px;
    font-family: DM Serif Display;
    font-size: 25px;
    font-weight: 400;
    line-height: 31px;
    letter-spacing: 0em;
    text-align: left;
    color: #292F36;
}

.footer__contact_text {
    margin-bottom: 35px;
    font-family: Jost;
    font-size: 22px;
    font-weight: 400;
    line-height: 33px;
    letter-spacing: 0.01em;
    text-align: left;
    color: #4D5053;
}

.footer__contact_telephon {
    font-family: Jost;
    font-size: 22px;
    font-weight: 400;
    line-height: 66px;
    letter-spacing: 0.01em;
    text-align: left;
    color: #4D5053;
}
</style>