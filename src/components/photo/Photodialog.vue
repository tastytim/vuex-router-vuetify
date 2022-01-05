<template>
  <v-dialog 
  v-model="$store.getters.getDialogVisible"
   max-width="600"
   @click:outside="$store.commit('hideDialog')"
   >
    <v-card>
      <v-card-title>{{ $store.getters.getCurrentPhoto.title }}</v-card-title>
      <v-card-text>
        <v-img
        
          :src="$store.getters.getCurrentPhoto.url"
        >
        </v-img>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {

};
</script>

<style></style>
