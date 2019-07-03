<template>
    <v-card class="message-card" color="#26c6da" dark max-width="400" hover>
        <v-card-text class="headline font-weight-bold">
          {{this.message}}
        </v-card-text>
    
        <v-card-actions>
          <v-list-tile class="grow">
            <v-list-tile-avatar color="grey darken-3">
              <v-img
                class="elevation-6"
                :src="this.icon"
              ></v-img>
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title>{{this.name}}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-card-actions>
  </v-card>
</template>
<script>
    export default{
       props:{
           name:String,
           message:String,
           icon:String
       }
    }
</script>
<style>
    .message-card{
        margin-top:15px;
        margin:0 0 auto 0;
        border-radius:40px;
    }    
</style>
