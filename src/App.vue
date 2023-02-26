<template>
    <the-header title="Learn Vue with..."></the-header>
    <the-resources></the-resources>
</template>

<script>
// import ResourceItem from './components/learning-resources/ResourseItem.vue'
import TheHeader from './components/UI/TheHeader.vue'
import TheResources from './components/learning-resources/TheResources.vue'
export default {
        components: {
            // 'resource-item': ResourceItem,
          
            'the-header': TheHeader,
            'the-resources': TheResources
            
        },
       
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