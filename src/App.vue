<template>
  <div>
    <div class="has-background-dark hero is-fullheight is-family-code">
      <!-- <DefaultLayout /> -->
      <div class="main-content columns">
        <router-view name="BoardLayout" 
          class="column is-2 is-narrow-mobile is-fullheight section is-hidden-mobile" />
        <router-view 
          class="container column is-10 p-5"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// import DefaultLayout from './layouts/DefaultLayout.vue';

export default defineComponent({
  components: {
    // DefaultLayout,
  },
});
</script>

<style lang="scss">
</style>

