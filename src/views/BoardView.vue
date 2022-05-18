<template>
  <div v-if="!isCreatingNote && notes.length === 0"
    class="columns is-vcentered has-text-centered mb-0">
    <div class="column">
      <img src="@/assets/img/icons/empty.png"
        style="width: 4rem; height: auto">
      <p class="mb-3">
        Empty list
      </p>

      <div class="is-fab is-flex is-justify-content-end">
        <button class="button is-primary is-rounded is-outlined"
          v-on:click="toggleCreateNote()">
          <span class="icon">
            <i class="fa-solid fa-plus"></i>
          </span>
        </button>
      </div>
    </div>
  </div>
  <div v-else
    class="columns mb-0">
    <div class="column is-3" v-for="note in formattedNotes" :key="note.id">
      <div class="card has-background-grey-dark has-text-white">
        <div class="card-content p-4">
          <p class="has-text-weight-bold has-text-white mb-3">
            {{ note.id }}
          </p>
          <p class="has-text-weight-bold has-text-white mb-3">
            {{ note.note }}
          </p>
          <p class="has-text-weight-bold has-text-white">
            {{ note.lastModifiedAt }}
          </p>

          <!-- <div class="is-flex is-justify-content-end">
            <button
              class="button is-white is-outlined is-small"
              v-on:click="toggleCreateNote()">
              <span class="icon">
                <i class="fa-solid fa-trash-can"></i>
              </span>
            </button>
            <button
              class="button is-primary is-outlined is-small ml-3"
              v-on:click="createNote()">
              <span class="icon">
                <i class="fa-solid fa-floppy-disk"></i>
              </span>
            </button>
          </div> -->
        </div>
      </div>
    </div>

    <div class="column is-3">
      <div class="card has-background-grey-dark has-text-white">
        <div class="card-content p-4">
          <p class="has-text-weight-bold has-text-white mb-3">
            New note
          </p>
          <div class="field">
            <div class="control">
              <textarea class="textarea has-background-grey-darker"
                placeholder="Type your note..."
                v-model="noteForm.message"></textarea>
            </div>
          </div>

          <div class="is-flex is-justify-content-end">
            <button
              class="button is-white is-outlined is-small"
              v-on:click="toggleCreateNote()">
              <span class="icon">
                <i class="fa-solid fa-trash-can"></i>
              </span>
            </button>
            <button
              class="button is-primary is-outlined is-small ml-3"
              v-on:click="createNote()">
              <span class="icon">
                <i class="fa-solid fa-floppy-disk"></i>
              </span>
            </button>
          </div>
        </div>
      </div>
      <div class="is-fab is-flex is-justify-content-end">
        <button class="button is-primary is-rounded is-outlined"
          v-on:click="toggleCreateNote()">
          <span class="icon">
            <i class="fa-solid fa-plus"></i>
          </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

interface Note {
  id: number,
  note: string | undefined,
  lastModifiedAt: string
}

@Options({ })
export default class BoardView extends Vue {

  // Data
  public notes = [] as Note[]

  // Checker
  public isCreatingNote = false as boolean
  
  // Form
  public noteForm = {
    message: undefined
  }

  public toggleCreateNote() {
    const currentDate = new Date()
    console.log(!this.isCreatingNote, this.notes.length, currentDate.toISOString())
    return this.isCreatingNote = !this.isCreatingNote
  }

  public createNote() {
    const currentDate = new Date()
    this.notes.push({
      id: this.notes.length + 1,
      note: this.noteForm.message,
      lastModifiedAt: currentDate.toISOString()
    })

    this.resetForm()
    return this.toggleCreateNote()
  }

  public resetForm() {
    return this.noteForm = {
      message: undefined
    }
  }

  // Computed
  get formattedNotes(): Note[] {
    return this.notes.map(item => {
      item.lastModifiedAt = new Date(item.lastModifiedAt).toLocaleString()
      return item
    })
  }
}
</script>

<style lang="scss" scoped>
.is-fab {
  width: 100%;
  position: fixed;
  bottom: 1.25rem !important;
  right: 1.25rem !important;
}
</style>