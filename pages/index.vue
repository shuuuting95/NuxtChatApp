<template>
  <v-container grid-list-md text-xs-left>
    <v-layout row column align-right>
      <div  v-for="message in messages" v-bind:key="message.messageId">
        <v-flex md12> 
          <MessageCard v-bind:class="{ 'my-message': message.name== name }" :name=message.name :message=message.message />
        </v-flex>
      </div>
    </v-layout>
    <v-layout row column align-right>
      <v-flex md12 class="send-message-area">
          <SendMessageArea />
      </v-flex>
    </v-layout>
    
  </v-container>
</template>

<script>
import MessageCard from '@/components/MessageCard.vue'
import SendMessageArea from '@/components/SendMessageArea.vue'
export default {
  components: {
    MessageCard,
    SendMessageArea
  },
   data: () => ({
     name:'Tanaka',
     messages: [
         { messageId: 1, name: 'Yamada', message: 'Hello'},
         { messageId: 2, name: 'Tanaka', message: 'hello world' }
      ]
   })
}
</script>
<style>
.my-message{
        margin:0 0 0 auto;
}
</style>
