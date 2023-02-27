<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-res')" :mode="storedResBtnMode">
        Stored Resources
        </base-button>
        <base-button @click="setSelectedTab('add-res')" :mode="addResBtnMode">
        Add Resources
        </base-button> 
    </base-card>
    <keep-alive><component :is="selectedTab"></component></keep-alive>
    
</template>

<script>
import StoredRes from './StoredRes.vue';
import AddRes from './AddResource.vue'
export default{
    components: {
          'stored-res': StoredRes,
          'add-res': AddRes
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            
                storedResources: [
                    {
                        id:'official-guide',
                        title: 'official guide',
                        description: 'adf',
                        link: 'fv'
                    },
                    {
                        id:'google',
                        title: 'google',
                        description: 'adf',
                        link: 'fv'
                    }
                ]
            
        
        };
    },
    provide()
    {
        return {
            resources: this.storedResources,
            addResFunc: this.addResourceFunc,
            delResFunc: this.deleteResFunc
        }
    },
    computed: {
        storedResBtnMode () {
            return this.selectedTab === 'stored-res' ? null : 'flat'
        },
        addResBtnMode () {
            return this.selectedTab === 'add-res' ? null : 'flat'
        },
    },
    methods: {
        setSelectedTab(tab){
            this.selectedTab=tab
        },
        addResourceFunc(title, desc, link) {
            const newRes = {
                id: new Date().toISOString(),
                title: title,
                description: desc,
                link: link
                
            }
            this.storedResources.unshift(newRes)
            this.selectedTab = 'stored-res'
        },
        deleteResFunc(resId){
            const resIn = this.storedResources.findIndex(res=>res.id === resId)
            this.storedResources.splice(resIn,1)
        }
    }
}
</script>