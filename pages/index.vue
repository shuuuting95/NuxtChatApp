<template>
  <v-container grid-list-md text-xs-left>
    <v-layout row column align-right>
      <div  v-for="message in messages" v-bind:key="message.messageId">
        <v-flex md12> 
          <MessageCard v-bind:class="{ 'my-message': message.name== name }" :name=message.name :message=message.message :icon=icon class="icon"/>
        </v-flex>
      </div>
    </v-layout>
    <v-layout row column align-right>
      <v-flex md12 class="send-message-area">
          <SendMessageArea @testWords="testMethods"/>
      </v-flex>
    </v-layout>
    <Dialog />
    
  </v-container>
</template>

<script>
import MessageCard from '@/components/MessageCard.vue'
import SendMessageArea from '@/components/SendMessageArea.vue'
import Dialog from '@/components/Dialog.vue'
export default {
  components: {
    MessageCard,
    SendMessageArea,
    Dialog
  },
   data: () => ({
     dialog: true,
     name:'',
     icon:"https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light",
     messages: [
         { messageId: 1, name: 'Yamada', message: 'Hello'},
         { messageId: 2, name: 'Tanaka', message: 'hello world'}
      ]
   }),
   methods:{
     testMethods(newMessage){
       console.log("ボタン押されたよ", newMessage)
       const newMessageObj ={
         messageId: 3,
         name: this.name,
         message: newMessage
       }
       this.messages.push(newMessageObj)
     }
   }
}
</script>
<style>
.my-message{
        margin:0 0 0 auto;
}
</style>
