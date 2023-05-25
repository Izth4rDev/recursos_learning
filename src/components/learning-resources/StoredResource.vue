<template>
    <ul>
        <list-resource v-for="resource in resources" :key="resource.id"
            :tittle="resource.tittle"
            :description="resource.decription"
            :link="resource.link"
        ></list-resource>
    </ul>
</template>

<script>

import ListResource from './ListResource.vue';

export default{
    components:{
        ListResource
    },
    inject:['resources'] //array inyectado desde TheResourceChange.vue
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>