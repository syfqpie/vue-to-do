<template>
    <div class="px-5 py-6 box mb-0 is-radiusless">
        <button
            class="button is-primary is-outlined mb-3 is-fullwidth"
            v-on:click="openCreateFolderOpen()">
            <span class="icon">
                <i class="fa-solid fa-plus"></i>
            </span>
            <span>
                Add new
            </span>
        </button>
        <aside class="menu">
            <p class="menu-label">
                General
            </p>
            <ul class="menu-list">
                <li>
                    <a>Dashboard</a>
                </li>
                <li>
                    <a>Customers</a>
                </li>
            </ul>
            <p class="menu-label">
                Administration
            </p>
            <ul class="menu-list">
                <li>
                    <a>Team Settings</a>
                </li>
                <li>
                    <a class="is-active is-primary">Manage Your Team</a>
                    <ul>
                        <li>
                            <a>Members</a>
                        </li>
                        <li>
                            <a>Plugins</a>
                        </li>
                        <li>
                            <a>Add a member</a>
                        </li>
                    </ul>
                </li>
                <li>
                    <a>Invitations</a>
                </li>
                <li>
                    <a>Authentication</a>
                </li>
            </ul>
            <p class="menu-label">
                Transactions
            </p>
            <ul class="menu-list">
                <li>
                    <a>Payments</a>
                </li>
                <li>
                    <a>Transfers</a>
                </li>
                <li>
                    <a>Balance</a>
                </li>
            </ul>
        </aside>
        
        <ModalComponent ref="modalComponent">
            <template #header>
            <p class="modal-card-title has-text-white has-text-left">
                New folder
            </p>
            </template>

            <template #content>
            <input 
                type="text"
                placeholder="Eg: New folder"
                class="input has-background-grey-darker"
                v-model="folderForm.name" />
            </template>

            <template #footer>
            <button class="button is-primary is-outlined"
                v-on:click="createFolder()">
                Save
            </button>
            </template>
        </ModalComponent>
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import ModalComponent from '@/components/ModalComponent.vue';

interface FolderName {
  name: string | null
}

@Options({
  components: {
    ModalComponent,
  }
})
export default class BoardLayout extends Vue {
  
  // Components
  modalComponent: typeof ModalComponent = ModalComponent

  // Form
  public folderForm: FolderName = {
    name: null
  }

  public openCreateFolderOpen() {
    console.log(this.folderForm);
    this.modalComponent.open()
  } 

  public createFolder() {
    console.log(this.folderForm);
    this.modalComponent.close()
  }
}
</script>