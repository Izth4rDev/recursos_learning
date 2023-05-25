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
    props:['resources']
}
</script>