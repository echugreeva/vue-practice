<template>
    <the-header title="Learn Vue with..."></the-header>
    <stored-res :resources="storedResources"></stored-res>
</template>

<script>
// import ResourceItem from './components/learning-resources/ResourseItem.vue'
import TheHeader from './components/UI/TheHeader.vue'
import StoredRes from './components/learning-resources/StoredRes.vue'

export default {
        components: {
            // 'resource-item': ResourceItem,
            'stored-res': StoredRes,
            'the-header': TheHeader,
            
        },
        data () {
            return {
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
            }
        }
    }
</script>

<style>
    * {
        box-sizing: border-box;
    }
    html {
        font-family: 'Roboto', sans-serif;
    }

    body {
        margin: 0
    }
</style>