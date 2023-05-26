<template>
    <base-card>
        <base-button @click="setSelectedTab('StoredResource')" :mode="setStoredButton">Recursos Guardados</base-button>
        <base-button @click="setSelectedTab('AddResources')" :mode="setAddButton">Añadir Recurso</base-button>
    </base-card>
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
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
                        title:'official Guide',
                        description:'The official Vue.js documentation', 
                        link:'https://vuejs.org'
                    },
                    {
                        id:'Google',
                        title:'Google',
                        description:'Learn to google', 
                        link:'https://google.com'
                    },
                ]
            }
        },
        provide(){ //metodo para inyectar recursos y metodos en componentes hijos
            return{
                resources: this.storedResources,//inyectamos el array en el componente StoredResource.vue
                addRe: this.addResource,//inyectamos el metodo addResource en el componente addResource
                removeRes: this.removeResource//Inyectamos el array en el componente ListResource
            };
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
            },
            addResource(title, description, url){
                const newResource = {
                    id: new Date().toISOString(),
                    title: title,
                    description: description,
                    link: url
                }
                this.storedResources.unshift(newResource);
                this.selectedTab = 'StoredResource'
            },
            removeResource(resId){
                const resIndex = this.storedResources.findIndex( res => res.id === resId);
                this.storedResources.splice(resIndex, 1);
            }
        }
    }
</script>

data(){
    return{
        s
    }
}