<template>
  <p class="text-blue-700 text-xl mb-3">
    <HelloWorld msg="Welcome to Vue TypeScript App"/>
  </p>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'HomeView',
  components: {
    HelloWorld,
  },
});
</script>
