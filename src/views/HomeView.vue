<template>
  <div class="container is-fullhd">
    <div id="top" class="hero is-fullheight">
      <div class="columns my-auto">
        <div class="column">
          <h1 class="is-size-1 has-text-white has-text-weight-bold
            is-family-code mb-3 has-text-centered">
              Welcome, young padawan~
          </h1>
          
          <div class="has-text-centered">
            <img src="@/assets/img/r2d2.png"
              style="width: 8rem; height: auto;"
              class="mb-3">
            <br/>

            <router-link to="/board" custom v-slot="{ navigate }">
              <button @click="navigate" @keypress.enter="navigate" role="link"
                class="button is-primary is-outlined is-family-code mb-3">
                Click to start
              </button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

@Options({
  components: {
    // HelloWorld,
  },
})
export default class HomeView extends Vue {}
</script>
