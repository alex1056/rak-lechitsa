<template>
  <router-link
    :to="{ path: `/stories/${storyData.id}` }"
    class="story"
    @click="$emit('click', storyData.id)"
  >
    <div class="story__img-container">
      <img
        class="story__img"
        :src="combineUrl()"
        alt="'Должен быть Alt text'"
      />
      <!-- <img
        class="story__img"
        src="https://images.unsplash.com/photo-1578496781985-452d4a934d50?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2700&q=80"
        alt="'Должен быть Alt text'"
      /> -->
      <!-- <img class="story__img" v-bind:alt="storyData.photo_alt" /> -->

      <!-- <img
        class="story__img"
        v-bind:src="`${process.env.apiUrl}${storyData.ImageUrl[0].url}`"
        v-bind:alt="storyData.photo_alt"
      /> -->
    </div>
    <h4 class="story__name">{{ storyData.author }}</h4>
    <p class="story__text">{{ storyData.title }}</p>
  </router-link>
</template>

<script>
export default {
  props: ['storyData'],
  methods: {
    combineUrl() {
      //storyData.ImageUrl[0].url
      // console.log('process.env.BASE_URL =', process.env.BASE_URL);
      // console.log('process.env.BASE_URL =', $env.BASE_URL);
      return process.env.BASE_URL + this.storyData.ImageUrl[0].url;
      // return 'https://strapi.kruzhok.io/stories';
    },
  },
  data() {
    return {
      // url: `/stories/${storyData.story_id}`,
      fetchUrl: 'https://strapi.kruzhok.io/stories',
    };
  },
};
</script>

<style scoped>
.story {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  cursor: pointer;
  text-decoration: none;
}

.story__img-container {
  width: 100%;
  position: relative;
}
.story__img-container:after {
  content: '';
  display: block;
  padding-bottom: 100%;
}
.story__img {
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.story__name {
  font-family: 'Inter';
  font-style: normal;
  font-weight: 600;
  font-size: 22px;
  line-height: 22px;
  color: #000;
  margin-top: 20px;
}

.story__text {
  font-family: Inter;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  color: #666;
  margin-top: 14px;
}

@media (max-width: 1280px) {
  .story {
    max-width: 265px;
  }

  .stories__title {
    max-width: 413px;
    font-size: 28px;
    line-height: 32px;
  }
  .stories__list {
    margin-top: 60px;
  }
}
@media (max-width: 1024px) {
  .story {
    max-width: 208px;
  }

  .story__name {
    font-size: 18px;
    line-height: 22px;
    margin-top: 16px;
  }

  .story__text {
    font-size: 13px;
    line-height: 16px;
    margin-top: 16px;
  }
}
@media (max-width: 768px) {
  .story {
    max-width: 216px;
    padding-bottom: 40px;
  }

  .story__name {
    font-size: 18px;
    line-height: 22px;
    margin-top: 16px;
  }

  .story__text {
    font-size: 13px;
    line-height: 16px;
    margin-top: 16px;
  }
}
@media (max-width: 425px) {
  .story {
    max-width: 100%;
    padding-bottom: 30px;
  }
  .story:last-child {
    padding-bottom: 40px;
  }
}
</style>
