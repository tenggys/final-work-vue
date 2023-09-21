<template>
<div>
    <section class="projects-intro">
        <div class="projects-intro__content">
            <div class="projects-intro__title-content">
                <h2 class="projects-intro__heading">Our Project</h2>
                <ul class="projects-intro__breadcrumbs">
                    <li class="projects-intro__breadcrumbs-item">
                        <router-link to="/" class="projects-intro__breadcrumbs-link">Home</router-link>
                    </li>
                    <li class="projects-intro__breadcrumbs-item">
                        <a href="#" class="projects-intro__breadcrumbs-link">Project</a>
                    </li>
                </ul>
            </div>
        </div>
    </section>
    <div class="projects center">
        <div class="projects__content">
            <div class="categories">
                <div class="categories__content">
                    <button v-for="button in listOfButtons" :key="button.id" @click="changeCurrentCategoryList(button.id)"
                        type="button"
                        :class="['categories__btn', button.id === buttonIsActive ? 'categories__btn_active' : false]">
                        {{ button.title }}
                    </button>
                </div>
            </div>
            <div class="projects__items">
                <div v-for="project in displayedCards" :key="project.id" class="projects__item">
                    <div class="star-box">
                        <svg @click="changeStarColor" class="star" :id="project.id" width="36" height="35"
                            viewBox="0 0 36 35" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <g filter="url(#filter0_d_993_156)">
                                <path
                                    d="M16.0992 1.80951C16.7004 -0.0279021 19.2996 -0.0279021 19.9008 1.80951L21.7983 7.60879C22.0673 8.43084 22.8342 8.98685 23.6992 8.98685H29.8097C31.7506 8.98685 32.5539 11.4732 30.98 12.6088L26.0604 16.1581C25.3546 16.6674 25.0591 17.5748 25.3298 18.402L27.2146 24.1623C27.8166 26.0025 25.7137 27.539 24.1435 26.4062L19.1702 22.818C18.4715 22.3139 17.5285 22.3139 16.8298 22.818L11.8565 26.4062C10.2863 27.539 8.18335 26.0025 8.78545 24.1623L10.6702 18.402C10.9409 17.5748 10.6454 16.6674 9.93955 16.1581L5.02004 12.6088C3.44611 11.4732 4.24942 8.98685 6.19025 8.98685H12.3008C13.1658 8.98685 13.9327 8.43084 14.2017 7.60879L16.0992 1.80951Z"
                                    fill="white" />
                            </g>
                            <defs>
                                <filter id="filter0_d_993_156" x="0.186424" y="0.431396" width="35.6271" height="34.3619"
                                    filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                                    <feFlood flood-opacity="0" result="BackgroundImageFix" />
                                    <feColorMatrix in="SourceAlpha" type="matrix"
                                        values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha" />
                                    <feOffset dy="4" />
                                    <feGaussianBlur stdDeviation="2" />
                                    <feComposite in2="hardAlpha" operator="out" />
                                    <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0" />
                                    <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_993_156" />
                                    <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_993_156"
                                        result="shape" />
                                </filter>
                            </defs>
                        </svg>
                    </div>
                    <img class="projects__item-image" :src="project.src" :alt="project.alt">
                    <div class="projects__item-content">
                        <div class="projects__item-box">
                            <p class="projects__item-title">{{ project.firstparagraph }}</p>
                            <p class="projects__item-subtitle">{{ project.secondparagraph }}</p>
                        </div>
                        <router-link to="/projectdetails"  class="projects__item-button">
                            <svg width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M1.27101 14.9525L7.21387 8.26683L1.27101 1.58112" stroke="#292F36" stroke-width="2"
                                    stroke-linecap="round" stroke-linejoin="round" />
                            </svg>
                        </router-link>
                    </div>
                </div>

            </div>
            <PaginationComp :totalNumberPaginationPages="setTotalNumberOfPages()" :currentPage="currentPage"
                @pagechanged="changeCurrentPage" />
        </div>
    </div>
</div>
</template>

<script>
import PaginationComp from '../components/PaginationComp.vue';
import { mapGetters } from 'vuex';

export default {
    name: 'ProjectView',

    components: {
        PaginationComp
    },

    data() {
        return {
            currentPage: 1,
            limitOfCardsPerPage: 8,

            currentCategoryList:
                [
                    { id: '65', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen1.png'), alt: 'kitchen one', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '66', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen2.png'), alt: 'kitchen two', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '67', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen3.png'), alt: 'kitchen three', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '68', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen4.png'), alt: 'kitchen four', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '69', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen5.png'), alt: 'kitchen five', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '70', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen6.png'), alt: 'kitchen six', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '71', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen7.png'), alt: 'kitchen seven', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '72', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen8.png'), alt: 'kitchen eight', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },


                    { id: '73', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen1.png'), alt: 'kitchen nine', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '74', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen2.png'), alt: 'kitchen ten', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '75', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen1.png'), alt: 'kitchen eleven', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '76', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen2.png'), alt: 'kitchen twelve', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '77', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen2.png'), alt: 'kitchen thirteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '78', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen1.png'), alt: 'kitchen fourteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '79', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen2.png'), alt: 'kitchen fifteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '80', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen1.png'), alt: 'kitchen sixteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },


                    { id: '81', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen3.png'), alt: 'kitchen seventeen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '82', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen4.png'), alt: 'kitchen eighteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '83', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen3.png'), alt: 'kitchen nineteen', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '84', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen4.png'), alt: 'kitchen twenty', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '85', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen4.png'), alt: 'kitchen twenty-one', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '86', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen3.png'), alt: 'kitchen twenty-two', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '87', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen4.png'), alt: 'kitchen twenty-three', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                    { id: '88', tag: 'kitchen', src: require('../assets/img//project/projects_kitchen3.png'), alt: 'kitchen twenty-four', firstparagraph: 'Modern Kitchen', secondparagraph: 'Decor / Artchitecture' },
                   ],

            listOfButtons:
                [
                    { id: 'bathroom', title: 'Bathroom' },
                    { id: 'bedroom', title: 'Bedroom' },
                    { id: 'kitchen', title: 'Kitchen' },
                    { id: 'livingroom', title: 'LivingArea' }
                ],
            buttonIsActive: 'kitchen',
        };
    },
    methods: {
        setTotalNumberOfPages() {
            return Math.ceil(this.currentCategoryList.length / this.limitOfCardsPerPage);
        },
        paginateListOfCards(currentCategoryList) {
            const newList = currentCategoryList;
            console.log(newList);
            let page = this.currentPage;
            let perPage = this.limitOfCardsPerPage;
            let from = (page * perPage) - perPage;
            let to = (page * perPage);
            return newList.slice(from, to);
        },
        changeCurrentPage(page) {
            console.log(page)
            this.currentPage = page;
        },
        changeCurrentCategoryList(id) {
            const buttonId = id;
            this.currentCategoryList = [];
            this.getAllCategoriesList.forEach(category => {
                if (category.tag === buttonId) {
                    this.buttonIsActive = buttonId;
                    return this.currentCategoryList.push(category);
                }

            });
        },
          changeStarColor(e) {
            const star = e.target.closest('.star');
            this.currentCategoryList.forEach((project) => {
                if (star.id === project.id) {
                    star.classList.toggle('star_active');
                }
            });
        },
    },
    computed: {
        displayedCards() {
            return this.paginateListOfCards(this.currentCategoryList);
        },
        ...mapGetters(['getAllCategoriesList', 'getCurrentCategoryList']),

    }
};
</script>


<style>

.center {
  padding-left: calc(50% - 600px);
  padding-right: calc(50% - 600px);
}

.projects-intro {
  margin-bottom: 200px;
}
.projects-intro__content {
  background-image: url("../assets/img/project/project_banner.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  justify-content: center;
}
.projects-intro__title-content {
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
.projects-intro__heading {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50px;
  line-height: 1.25;
  margin: 0;
}
.projects-intro__breadcrumbs {
  margin: 0;
  padding: 0;
}
.projects-intro__breadcrumbs-item {
  display: inline-block;
  align-items: center;
}
.projects-intro__breadcrumbs-item:not(:last-child)::after {
  content: "/";
  margin-left: 8px;
  margin-right: 8px;
}
.projects-intro__breadcrumbs-link {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  transition: all 0.5s ease-out;
}
.projects-intro__breadcrumbs-link:hover {
  color: #CDA274;
  transition: all 0.8s ease-out;
}
.projects-intro__breadcrumbs-link:active {
  color: #4D5053;
  transition: all 0.8s ease-out;
}
.projects-intro__breadcrumbs-link:focus {
  color: #CDA274;
  transition: all 0.8s ease-out;
}


.projects {
  margin-bottom: 200px;
}
.projects__items {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  gap: 30px;
  max-height: 3230px;
  margin-bottom: 61px;
}
.projects__item {
  position: relative;
}
.projects__item-image {
  display: flex;
  max-width: 585px;
}
.projects__item-content {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding-top: 22px;
}
.projects__item-box {
  display: flex;
  min-width: 290px;
  height: 70px;
  flex-direction: column;
  align-items: flex-start;
  gap: 10px;
  align-content: flex-start;
  justify-content: flex-end;
}
.projects__item-title {
  color: #292F36;
  font-family: " DM Serif Display", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 25px;
  line-height: 1.25;
  letter-spacing: 0.5px;
  margin: 0;
}
.projects__item-subtitle {
  color: #4D5053;
  font-family: "Jost", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 22px;
  line-height: 1.5;
  letter-spacing: 0.22px;
  margin: 0;
}
.projects__item-button {
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
.projects__item-button:hover {
  background-color: #FFFFFF;
  border: 1px solid #E7E7E7;
  transition: all 0.8s ease-out;
}
.projects__item-button:active {
  background-color: #4D5053;
  border: none;
  transition: all 0.8s ease-out;
}
.projects__item-button:focus {
  background-color: #CDA274;
  border: none;
  transition: all 0.8s ease-out;
}


.star-box {
  position: absolute;
  top: 5px;
  right: 5px;
}

.star_active path {
  fill: #FFA928;
}


.categories__content {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  flex-wrap: nowrap;
  border-radius: 18px;
  border: 1px solid #CDA274;
  margin-left: 140px;
  margin-right: 140px;
  margin-bottom: 61px;
}


.categories__btn {
  color: #292F36;
  font-family: "Jost", sans-serif;
  font-weight: 600;
  font-style: normal;
  font-size: 18px;
  line-height: 1.25;
  text-align: center;
  letter-spacing: 0.36px;
  border: none;
  border-radius: 18px;
  background-color: #FFFFFF;
  padding: 26px 66px;
  width: 230px;
}
.categories__btn:hover {
  background-color: #CDA274;
}
.categories__btn:focus {
  color: #FFFFFF;
  background-color: #292F36;
}
.categories__btn_active {
  color: #FFFFFF;
  background-color: #292F36;
}
</style>