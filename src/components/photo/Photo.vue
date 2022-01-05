<template>
  <v-col cols="3" class="d-flex">
    <v-card
    
    class="mx-auto "
    
  >
    <v-img
      @click="openPhoto"
      :src="photo.url"
      cover
      min-height="272"
    ></v-img>

    <v-card-title>
      {{photo.title}}
    </v-card-title>
     <v-card-text>
        <v-row
          align="center"
          class="mx-0"
        >
          <v-rating
            :value="4.5"
            color="amber"
            dense
            half-increments
            readonly
            size="14"
          ></v-rating>
  
          <div class="grey--text ms-4">
            4.5 (413)
          </div>
        </v-row>
        </v-card-text>

    <v-card-actions>
      <v-btn
        color="blue lighten-2"
        text
      >
        Explore
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          {{photo.title}}
        </v-card-text>
      </div>
    </v-expand-transition>

  </v-card>
  </v-col>
</template>

<script>
import {mapMutations} from 'vuex';
export default {
  props: {
    photo: {
      type: Object,
      required: true,
    },
  },
  data: ()=> ({
     show: false,
  }),
  methods:{
    ...mapMutations(['setCurrentPhoto', 'showDialog','hideDialog']),
      openPhoto(){
          this.setCurrentPhoto(this.photo);
          this.showDialog();
      }
  }
};
</script>

<style></style>
