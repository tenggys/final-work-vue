<template>
    <div class="blog__items center">
      <div v-for="item in getlistOfBlogs" :key="item" class="article-card__item">
          <img :src="item.src" :alt="item.alt" class="article-card__item-image">
          <div class="article-card__item-tagbox">
              <p class="article-card__item-tag">{{ item.tag }}</p>
          </div>
          <div class="item-content">
              <p class="item-content__title">{{ item.title }}</p>
              <div class="item-content__box">
                  <p class="item-content__date">{{ item.date }}</p>
                  <router-link to="/blogdetails" class="item-content__button">
                      <svg width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                          <path d="M1.27101 14.9525L7.21387 8.26683L1.27101 1.58112" stroke="#292F36" stroke-width="2"
                              stroke-linecap="round" stroke-linejoin="round" />
                      </svg>
                  </router-link>
              </div>
          </div>
      </div>
    </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
    name: 'ArticleCardComp',

    props: {
        item:{
            type: Object
        }
    },
    computed: {
        ...mapGetters(['getlistOfBlogs'])
    }
};
</script>

<style>
.blog__items {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 27px;
}

.center {
  padding-left: calc(50% - 600px);
  padding-right: calc(50% - 600px);
}

.article-card__item {
  width: 382px;
}
.article-card__item {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 21px;
  padding: 21px;
  border-radius: 62px;
  border: 1px solid #E7E7E7;
  box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
  justify-content: center;
  align-items: center;
  transition: all 0.5s ease-out;
}
.article-card__item:hover {
  background-color: #F4F0EC;
  transition: all 0.8s ease-out;
}
.article-card__item:hover .item-content__button {
  background-color: #FFFFFF;
  transition: all 0.8s ease-out;
}
.article-card__item-image {
  display: flex;
  width: 100%;
}
.article-card__item-tagbox {
  position: absolute;
  top: 253px;
  left: 52px;
  background-color: #FFFFFF;
  padding: 4px 20px 8px 11px;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
}
.article-card__item-tag {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 16px;
  line-height: 1.5;
  letter-spacing: 0.16px;
  text-transform: capitalize;
  margin: 0;
}

.item-content {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  gap: 30px;
}
.item-content__box {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  min-width: 340px;
}
.item-content__title-box {
  display: flex;
  width: 305px;
  height: 70px;
  flex-direction: column;
  justify-content: center;
}
.item-content__title {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 25px;
  line-height: 1.25;
  letter-spacing: 0.5px;
  margin: 0;
}
.item-content__date {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 16px;
  line-height: 1.5;
  letter-spacing: 0.16px;
  text-transform: capitalize;
  margin: 0;
}
.item-content__button {
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  height: 52px;
  width: 52px;
  border-radius: 50%;
  background-color: #F4F0EC;
  cursor: pointer;
  padding: 0;
  transition: all 0.8s ease-out;
}
.item-content__button:active {
  background-color: #4D5053;
  transition: all 0.8s ease-out;
}
.item-content__button:focus {
  background-color: #CDA274;
  transition: all 0.8s ease-out;
}
</style>

