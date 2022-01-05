<template>
  
  <v-container>
      <Photoform class="py-15" @addPhoto="addPhoto"/>
    <v-row>
      <Photo v-for="photo in $store.getters.getAllPhotos" :key="photo.id" :photo="photo"></Photo>
    </v-row>
    <Photodialog/>
  </v-container>
</template>

<script>
import Photo from "@/components/photo/Photo.vue";
import Photoform from "@/components/photo/Photoform.vue";
import Photodialog from '../components/photo/Photodialog.vue';
import {mapActions} from 'vuex';

export default {
  components: {
    Photo,
    Photoform,
    Photodialog
  },
  data: () => ({
    photos: [],
    // currentPhoto : {},
    // dialogVisible:false
  }),
  mounted() {
     this.fetchPhotos()
    // this.fetchToDo();
  },
  methods: {
      ...mapActions(['fetchPhotos']),
    // fetchToDo() {
    //   this.axios
    //     .get("https://jsonplaceholder.typicode.com/photos?_limit=10")
    //     .then((response) => (this.photos = response.data));
    // },
  
    addPhoto(photo){
        this.$store.getters.getAllPhotos.push(photo);
    },
    openPhoto(photo){
        this.currentPhoto = photo,
        this.dialogVisible = true
    }
  },
};
</script>

<style scoped></style>
