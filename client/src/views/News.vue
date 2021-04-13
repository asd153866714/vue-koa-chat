<template>
<div class="warrper">
    <the-header :currentTab="currentTab"></the-header>
    <the-newssub></the-newssub>
    <the-newscontain></the-newscontain>
    <div class="contain">
      <ul class="media-list">
        <li class="media" v-for="article in articles" :key="article">
          <div class="media-left">
            <a v-bind:href="article.url" target="_blank">
              <img class="media-object" v-bind:alt="article.description" v-bind:src="article.image" />
            </a>
            <div class="aaa">
              <h4 class="media-heading">
              <a v-bind:href="article.url" target="_blank">{{article.title}}</a>
              <i class="author">{{article.source.name	}}</i>
            </h4>
            </div>
            
          </div>
          
        </li>
      </ul>
    </div>
    <the-footer :currentTab="currentTab"></the-footer>
</div>
    
</template>

<script>
import axios from 'axios';

import TheNewscontain from '../components/TheNewscontain.vue';
import TheNewssub from '../components/TheNewssub.vue';


export default {
  components: { TheNewssub, TheNewscontain },
    created(){
        this.category = this.$route.params.category;
        axios.get('https://gnews.io/api/v4/top-headlines?country=tw&topic=breaking-news&token=fce657bd48580e505cecf51d6a24d4fb')
        .then(response => {
            console.log(response)
            this.articles = response.data.articles
        });
    },
    data() {
    return {
      currentTab: 2,
      articles: [],
      category:' ',
    };
  },
   
};
</script>
<style lang="scss" scoped>

  .media-object {
    width: 128px;
    padding: 10px;
  }
  .media {
    background-color: black;
    border-top: 1px solid lightgrey;
    padding: 30px;
  }
  .author{
      padding-left: 1rem;
      color: red;
    }
  .media-heading{
    display: inline-block;
    padding-left: 1rem;
    text-align: center;
    
  }
</style>