<template>
<div class="warrper">
    <the-header :currentTab="currentTab"></the-header>
    <the-newssub></the-newssub>
    <div class="contain">
    
    </div>
    <the-footer :currentTab="currentTab"></the-footer>
</div>
    
</template>

<script>
import TheNewscontain from '../components/TheNewscontain.vue';
import TheNewssub from '../components/TheNewssub.vue';


export default {
  components: { TheNewssub, TheNewscontain },
  
    data() {
    return {
      currentTab: 2,
    };
  },
   
};
</script>
<style lang="scss" scoped>

</style>