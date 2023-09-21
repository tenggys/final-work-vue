<template>
<div>
    <div class="not-found center">
        <div v-for="info in notFoundInfo" :key="info.id" class="not-found__content">
            <div class="not-found__content_right">
                <p class="not-found__title">{{ info.title }}</p>
                <p class="not-found__text">{{ info.text }}</p>
                <BlackButtonComp :button-text="buttonText" :link="link" class="button"/>
            </div>
            <div class="not-found__content_left">
                <img class="not-found__image" :src="info.src" :alt="info.alt">
            </div>
        </div>
    </div>
</div>
</template>

<script>
import BlackButtonComp from '@/components/BlackButtonComp.vue';

export default {

    name: 'NotFound',

    components: {
        BlackButtonComp
    },

    data() {
        return {
            buttonText: 'Back To Home',
            link: '/',
            notFoundInfo: [
                {
                    title: '404',
                    text: 'We are sorry, but the page you requested was not found',
                    src: require('../assets/img/notFound/not_found_img.png'),
                    alt: "not-found picture"
                }
            ]
        };
    },
};
</script>

<style>

.not-found {
  margin-bottom: 200px;
}
.not-found__content {
  display: grid;
  grid-template-columns: 569px 913px;
  -moz-column-gap: 81px;
       column-gap: 81px;
}
.not-found__content_right {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}
.not-found__title {
  color: #CDA274;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 250px;
  line-height: 1.25;
  margin: 0;
  margin-bottom: 15px;
}
.not-found__text {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 35px;
  line-height: 1.5;
  letter-spacing: 0.35px;
  margin: 0;
  margin-bottom: 23px;
}
.not-found__image {
  width: 100%;
}
</style>