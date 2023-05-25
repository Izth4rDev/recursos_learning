<template>
    <base-card>
        <base-button @click="setSelectedTab('StoredResource')" :mode="setStoredButton">Recursos Guardados</base-button>
        <base-button @click="setSelectedTab('AddResources')" :mode="setAddButton">Añadir Recurso</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import StoredResource from './StoredResource.vue';
import AddResources from './AddResources.vue';
    export default{
        components:{
            StoredResource,
            AddResources
        },
        data(){
            return{
                selectedTab: 'StoredResource',
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
        },
        provide(){ //inyectamos el array en el componente StoredResource.vue
            return{
                resources: this.storedResources
            }
        },
        computed:{
            setAddButton(){
                return this.selectedTab === 'AddResources' ? null : 'flat';
            },
            setStoredButton(){
                return this.selectedTab === 'StoredResource' ? null : 'flat';
            }
        },
        methods:{
            setSelectedTab(tab){
                this.selectedTab = tab;
            }
        }
    }
</script>

data(){
    return{
        s
    }
}