<template>
  <div class="news">
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'business'}}"
      >商業</router-link
    >
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'health'}}"
      >健康</router-link
    >
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'science'}}"
      >科學</router-link
    >
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'technology'}}"
      >科技</router-link
    >
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'entertainment'}}"
      >娛樂</router-link
    >
    <router-link
      class="item"
      :to="{name: 'newsdetail', params: {category: 'sports'}}"
      >運動</router-link
    >
    
         
  </div>
</template>

<script>
export default {
  name: "NEWS",
  data() {
    return {};
  },
  computed: {
    category: function() {
    return this.$route.params.category;
    }
  },
  
};
</script>
<style lang="scss" scoped>
.news {
  width: 100%;
  position: fixed;
  top: 0.9rem;
}

.item {
  
  color: darkcyan;
  padding: 0.5rem;
  margin-left: 0.8rem;
  text-decoration: none;
  box-sizing: border-box;

}

</style>