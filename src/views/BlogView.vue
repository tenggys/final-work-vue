<template>
<div>
    <section class="intro">
        <div class="intro__content">
            <div class="intro__title-content">
                <h2 class="intro__heading">Articles & News</h2>
                <ul class="intro__breadcrumbs">
                    <li class="intro__breadcrumbs-item">
                        <router-link to="/" class="intro__breadcrumbs-link">Home</router-link>
                    </li>
                    <li class="intro__breadcrumbs-item">
                        <a href="#" class="intro__breadcrumbs-link">Blog</a>
                    </li>
                </ul>
            </div>
        </div>
    </section>
    <section class="post center">
        <div class="post__content">
            <h2 class="post__heading">Latest Post</h2>
            <div class="post__subcontent-box">
                <img src="../assets/img/blog/LatestPost.png" alt="post image">
                <article class="post__subcontent">
                    <div class="post__subcontent-container">
                        <h3 class="post__subcontent-heading">Low Cost Latest Invented Interior Designing Ideas</h3>
                        <p class="post__subcontent-text">Lorem ipsum dolor sit amet, adipiscing Aliquam eusem vitae turpis
                            dignissim maximus.posuere in. Contrary to popular belief.</p>
                        <p class="post__subcontent-text">Lorem Ipsum is not simply random text. It has roots in a piece of
                            classica.</p>
                    </div>
                    <div class="post__subtitle-box">
                        <p class="post__subcontent-subtitle">26 December,2022</p>
                        <button class="post__button">
                            <svg width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M1.27101 14.9525L7.21387 8.26683L1.27101 1.58112" stroke="#292F36" stroke-width="2"
                                    stroke-linecap="round" stroke-linejoin="round" />
                            </svg>
                        </button>
                    </div>
                </article>
            </div>
        </div>
    </section>
    <section class="news center">
        <div class="news__content">
            <h2 class="news__heading">Articles & News</h2>
            <div class="news__items">
                <BlogArticleCardComp  />
            </div>
            <PaginationComp :totalNumberPaginationPages="setTotalNumberOfPages()"
                :currentPage="currentPage"  @pagechanged="changeCurrentPage" />
        </div>
    </section>
</div>
</template>

<script>
import BlogArticleCardComp from '../components/BlogArticleCardComp.vue';
import PaginationComp from '../components/PaginationComp.vue';
import { mapGetters } from 'vuex';


export default {
    name: 'BlogView',

    components: {
      BlogArticleCardComp,
      PaginationComp
    },
    data() {
        return {
            currentPage: 1,
            limitOfCardsPerPage: 3,
        };
    },
    methods: {
        setTotalNumberOfPages() { 
            return Math.ceil(this.getListOfCards.length / this.limitOfCardsPerPage);
        },
        paginateListOfCards(listOfCards) {
            let page = this.currentPage;
            let perPage = this.limitOfCardsPerPage;
            let from = (page * perPage) - perPage;
            let to = (page * perPage);
            return listOfCards.slice(from, to);
        },
        changeCurrentPage(page) {
            console.log(page)
            this.currentPage = page;
        }
    },
    computed: {
        ...mapGetters(['getListOfCards']),
        displayedCards() {
            return this.paginateListOfCards(this.getListOfCards);
        }
    }
};
</script>

<style>

.center {
  padding-left: calc(50% - 600px);
  padding-right: calc(50% - 600px);
}

.intro {
  margin-bottom: 200px;
}
.intro__content {
  background-image: url("../assets/img/blog/blog__post.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  justify-content: center;
}
.intro__title-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 10px;
  width: 503px;
  padding: 41px 78px;
  border-radius: 37px 37px 0px 0px;
  background: #FFF;
  max-width: 503px;
  margin-top: 178px;
}
.intro__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 49px;
  line-height: 1.25;
  line-height: 1.25;
  margin: 0;
}
.intro__breadcrumbs {
  margin: 0;
  padding: 0;
}
.intro__breadcrumbs-item {
  display: inline-block;
  align-items: center;
}
.intro__breadcrumbs-item:not(:last-child)::after {
  content: "/";
  margin-left: 8px;
  margin-right: 8px;
}
.intro__breadcrumbs-link {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  transition: all 0.5s ease-out;
}
.intro__breadcrumbs-link:hover {
  color: #CDA274;
  transition: all 0.8s ease-out;
}
.intro__breadcrumbs-link:active {
  color: #4D5053;
  transition: all 0.8s ease-out;
}
.intro__breadcrumbs-link:focus {
  color: #CDA274;
  transition: all 0.8s ease-out;
}


.post {
  margin-bottom: 150px;
}
.post__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50px;
  line-height: 1.25;
  letter-spacing: 1px;
  margin: 0;
  margin-bottom: 27px;
}
.post__subcontent-box {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 65px;
  border-radius: 62px;
  border: 1px solid #E7E7E7;
  box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
  padding: 22px;
}
.post__subcontent {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  max-width: 489px;
  gap: 31px;
}
.post__subcontent-container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  max-width: 469px;
  gap: 22px;
}
.post__subcontent-heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 25px;
  line-height: 1.25;
  letter-spacing: 0.5px;
  margin: 0;
}
.post__subcontent-text {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
  margin-bottom: 10px;
}
.post__subtitle-box {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  min-width: 469px;
}
.post__subcontent-subtitle {
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
.post__button {
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  height: 52px;
  width: 52px;
  border-radius: 50%;
  background-color: #F4F0EC;
  cursor: pointer;
  transition: all 0.8s ease-out;
  padding: 0;
}
.post__button:hover {
  background-color: #FFFFFF;
  border: 1px solid #E7E7E7;
  transition: all 0.8s ease-out;
}
.post__button:active {
  background-color: #4D5053;
  border: none;
  transition: all 0.8s ease-out;
}
.post__button:focus {
  background-color: #CDA274;
  border: none;
  transition: all 0.8s ease-out;
}
.post__button:nth-child(1) {
  background-color: #FFFFFF;
}

.news {
  margin-bottom: 200px;
}
.news__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50px;
  line-height: 1.25;
  letter-spacing: 1px;
  margin: 0;
  margin-bottom: 30px;
}
.news__items {
  margin-bottom: 51px;
}
/*
.news__items {
  display: grid;
  grid-template-columns: repeat(3, 382px);
  grid-template-rows: repeat(2, auto);
  justify-content: center;
  align-content: center;
  gap: 27px;
  margin-bottom: 51px;
}*/
</style>
