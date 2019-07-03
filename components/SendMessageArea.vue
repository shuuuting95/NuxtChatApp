<template>
    <v-container fluid grid-list-md>
        <v-layout row wrap>
            <v-flex md10>
                <v-textarea solo name="input-7-4" label="メッセージを入力してください" v-model="message"></v-textarea>
            </v-flex>
            <v-btn class="send-button" color="info" md2 @click="sendMessage()">Send</v-btn>
        </v-layout>
  </v-container>
</template>
<script type="text/javascript">
    export default {
        data(){
            return {
                message: ''
            }
        },
        methods:{
            sendMessage(){
                this.$emit('testWords', this.message)
                this.message = ''
            }
        }
    }
    
</script>
<style>
.send-button{
    background-color:black;
    height:110px;
    padding:0;
    margin-top:5px;
}
</style>
