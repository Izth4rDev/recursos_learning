<template>
    <the-header :title="'RememberMe'"></the-header>
    <the-resource-change></the-resource-change>
</template>

<script>

import TheHeader from './components/layouts/TheHeader.vue';
import TheResourceChange from './components/learning-resources/TheResourceChange.vue';
export default{
    components:{
        TheHeader,
        TheResourceChange
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