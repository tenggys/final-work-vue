<template>
    <div>
        <div class="button__box">
            <button @click="$router.push(link)" class="button__content button__paddings">
                {{ buttonText }}
                <svg class="button__arrow" width="19" height="17" viewBox="0 0 19 17" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path d="M2 8.43542L15.7232 8.29857M10.6182 1.91138L17.1412 8.43436L10.4868 15.0887" stroke="#CDA274"
                        stroke-width="2" stroke-linecap="square" stroke-linejoin="round" />
                </svg>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlackButtonComp',

    props: {
        buttonText: {
            type: String,
            required: true
        },
        link: {
            type: String,
            required: true
        }
    }

};
</script>

<style>
.button__box {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-wrap: nowrap;
}

.button__content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: nowrap;
  box-sizing: border-box;
  border-radius: 18px;
  border: 1px solid #292F36;
  background: #292F36;
  box-shadow: 0px 10px 20px 0px rgba(192, 192, 192, 0.35);
  cursor: pointer;
  color: #FFFFFF;
  font-family: "Jost", sans-serif;
  font-weight: 600;
  font-style: normal;
  font-size: 18px;
  line-height: 1.25;
  letter-spacing: 0.36px;
  text-align: center;
}

.button__paddings {
    padding: 26px 31px 26px 48px;
}

.button__content:hover {
  color: #CDA274;
  background: #FFFFFF;
  border: 1px solid #292F36;
}

.button__content:focus {
  outline: none !important;
  fill: #FFFFFF;
}

.button__content:active {
  color: #CDA274;
  background: #FFFFFF;
  border: 1px solid #292F36;
  transition: all 0.5s ease-out;
}

.button__arrow {
  margin-left: 10px;
}
.button__arrow:hover path {
  transition: all 0.8s ease-out;
}
</style>

