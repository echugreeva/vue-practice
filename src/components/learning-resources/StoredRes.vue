<template>
    <ul>
        <resource-item v-for="res in resources" 
        :key="res.id" 
        :title ="res.title"
        :description="res.description"
        :link="res.link" ></resource-item>
    </ul>
</template>

<script>
import ResourceItem from './ResourseItem.vue'
export default {
  inject: ['resources'],
  components: {
    'resource-item': ResourceItem,
  }
};
</script>
