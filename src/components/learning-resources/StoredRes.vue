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
  props: ['resources'],
  components: {
    'resource-item': ResourceItem,
  }
};
</script>
