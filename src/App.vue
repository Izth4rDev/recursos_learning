<template>
    <stored-resource :resources="storedResources"></stored-resource>
</template>

<script>
import StoredResource from './components/learning-resources/StoredResource.vue';

export default{
    components:{
        StoredResource
    },
    data(){
        return{
            storedResources:[
                {
                    id:'official-guide',
                    tittle:'official Guide',
                    decription:'The official Vue.js documentation', 
                    link:'https://vuejs.org'
                },
                {
                    id:'Google',
                    tittle:'Google',
                    decription:'Learn to google', 
                    link:'https://google.com'
                },
            ]
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>