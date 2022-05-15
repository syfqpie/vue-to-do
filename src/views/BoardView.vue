<template>
  <div class="columns is-vcentered has-text-centered mb-0">
    <div class="column">
      <img src="@/assets/img/icons/empty.png"
        style="width: 4rem; height: auto">
      <p class="mb-3">
        Empty list
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({ })
export default class BoardView extends Vue {

}
</script>
