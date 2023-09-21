<template>
    <div>
        <section class="banner center">
            <div class="banner__content">
                <div class="banner__subcontent-box">
                    <div class="bunner__subcontent">
                        <h1 class="banner__subcontent-heading">Let Your Home Be Unique</h1>
                        <p class="banner__subcontent-text">There are many variations of the passages of lorem Ipsum
                            fromavailable, majority.</p>
                    </div>
                    <BlackButtonComp :button-text="buttonText" :link="link" class="button" />
                </div>
            </div>
        </section>
        <section class="project center">
            <div class="project__content">
                <h2 class="project__heading">Follow Our Projects</h2>
                <div class="project__text-box">
                    <p class="project__text">
                        It is a long established fact that a reader will be distracted by the of readable content of page
                        lookings at its layouts points.
                    </p>
                </div>
                <div class="project__items">
                    <div v-for="project in getListOfProjects" :key="project.id" class="project__item">
                        <img class="project__item-image" :src="project.src" :alt="project.alt">
                        <div class="project__item-content">
                            <div class="project__item-box">
                                <p class="project__item-title">{{ project.firstparagraph }}</p>
                                <p class="project__item-subtitle">{{ project.secondparagraph }}</p>
                            </div>
                            <router-link :to="secondLink" class="project__item-button">
                                <svg width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M1.27101 14.9525L7.21387 8.26683L1.27101 1.58112" stroke="#292F36" stroke-width="2"
                                        stroke-linecap="round" stroke-linejoin="round" />
                                </svg>
                            </router-link>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <div class="counter">
            <div class="counter__content">
                <div class="counter__content-items">
                    <div v-for="counter in listOfCounters" :key="counter.id" class="counter__content-item">
                        <p class="content-item__number">{{ counter.number }}</p>
                        <p class="content-item__text">{{ counter.text }}</p>
                    </div>
                </div>
            </div>
        </div>
        <section class="blog center">
            <div class="blog__content">
                <h2 class="blog__heading">Articles & News</h2>
                <div class="blog__text-box ">
                    <p class="blog__text">It is a long established fact that a reader will
                        be distracted by the of readable content of a page when lookings at its
                        layouts the points of using.</p>
                </div>
                <div class="blog__items">
                    <ArticleCardComp  />
                </div>
            </div>
        </section>
    </div>
</template>
    
<script>
    import ArticleCardComp from '../components/ArticleCardComp.vue'
    import BlackButtonComp from '../components/BlackButtonComp.vue';
    import { mapGetters } from 'vuex';
    
    export default {
        name: 'HomeView',
    
        components: {
            ArticleCardComp,
            BlackButtonComp
        },
    
        data() {
            return {
                buttonText: 'Get Started',
                link: '/project',
                secondLink: '/project',
               
                listOfCounters: [
                    {
                        id: 'first-counter', number: '12', text: 'Years Of Experiance'
                    },
                    {
                        id: 'second-counter', number: '85', text: 'Success Project'
                    },
                    {
                        id: 'third-counter', number: '15', text: 'Active Project'
                    },
                    {
                        id: 'fourth-counter', number: '95', text: 'Happy Customers'
                    }
                ],   
            };
        },
        
        computed: {
          ...mapGetters(['getListOfProjects'])
        },
    };
</script>
    
<style lang="css" scoped>
.banner {
  margin-bottom: 96px;
} 

.center {
  padding-left: calc(50% - 600px);
  padding-right: calc(50% - 600px);
}


.banner__content {
  position: relative;
  overflow: hidden;
  width: 100%;
  min-height: 758px;
  background-image: url("../assets/img/home/banner.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.banner__subcontent-box {
  position: absolute;
  top: 208px;
  left: 52px;
  display: grid;
  grid-template-columns: 434px;
  grid-template-rows: repeat(2, auto);
  gap: 21px;
}
.banner__subcontent-heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 65px;
  line-height: 1.25;
  margin: 0;
  margin-bottom: 18px;
}
.banner__subcontent-text {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
}


.project {
  margin-bottom: 96px;
}
.project__content {
  display: grid;
  justify-content: center;
}
.project__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50px;
  line-height: 1.25;
  text-align: center;
  letter-spacing: 1px;
  margin: 0;
  margin-bottom: 8px;
}
.project__text-box {
  display: block;
  margin: 0 auto;
  max-width: 737px;
  margin-bottom: 93px;
}
.project__text {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  text-align: center;
  letter-spacing: 0.22px;
  margin: 0;
}
.project__items {
  display: grid;
  grid-template-columns: repeat(2, 548px);
  justify-content: center;
  -moz-column-gap: 104px;
       column-gap: 104px;
  row-gap: 56px;
}
.project__item-image {
  display: flex;
  width: 100%;
}
.project__item-content {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding-top: 24px;
}
.project__item-box {
  display: flex;
  max-width: 217px;
  height: 70px;
  flex-direction: column;
  align-items: flex-start;
  gap: 10px;
  align-content: flex-start;
  justify-content: flex-end;
}
.project__item-title {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 25px;
  line-height: 1.25;
  letter-spacing: 0.5px;
  margin: 0;
}
.project__item-subtitle {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
}
.project__item-button {
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
.project__item-button:hover {
  background-color: #FFFFFF;
  border: 1px solid #E7E7E7;
  transition: all 0.8s ease-out;
}
.project__item-button:active {
  background-color: #4D5053;
  border: none;
  transition: all 0.8s ease-out;
}
.project__item-button:focus {
  background-color: #CDA274;
  border: none;
  transition: all 0.8s ease-out;
}


.counter {
  margin-bottom: 96px;
}
.counter__content {
  background-color: #F4F0EC;
  display: flex;
  justify-content: center;
  align-content: center;
  padding-top: 151px;
  padding-bottom: 151px;
}
.counter__content-items {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  gap: 76px;
}
.counter__content-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;
  padding-right: 80px;
  border-right: 1px solid #CDA274;
}
.counter__content-item:last-child {
  border: none;
}

.content-item__number {
  color: #CDA274;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 85px;
  line-height: 1.25;
  letter-spacing: 1.7px;
  margin: 0;
}

.content-item__text {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
}


.blog {
  margin-bottom: 96px;
}
.blog__content {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-content: center;
  align-items: center;
  flex-wrap: wrap;
}
.blog__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50px;
  line-height: 1.25;
  text-align: center;
  letter-spacing: 1px;
  margin: 0;
  margin-bottom: 12px;
}
.blog__text-box {
  display: block;
  margin: 0 auto;
  max-width: 811px;
  margin-bottom: 52px;
}
.blog__text {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
  text-align: center;
}
.blog__items {
  display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 27px;
}





</style>