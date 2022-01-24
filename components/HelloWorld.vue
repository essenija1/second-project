<template>
  <div class="hello">
    <teleport to=".my-div">
      <p>From Teleport</p>
    </teleport>
  </div>
  <button @click="toggleModal">Show/hide</button>
  <teleport to="#modal">
    <my-modal v-if="showModal">
      <p>Form Modal</p>
      <button @click="toggelModal">Close</button>
    </my-modal>
  </teleport>
  <br />
  {{ user }}
  <login-form v-model:username="user.name" v-model:password="user.password" />
  <br />
  <button @click="count++">{{ count }}</button>
  <button @click="addLink">Add Link</button>
  <button @click="removeLink">Remove Link</button>
  <my-button @custom-event-1="firstEvent" @custom-event-2="secondEvent" />
</template>

<script setup>
import MyButton from "./MyButton.vue";
import MyModal from "./MyModal.vue";
import LoginForm from "./LoginForm.vue";
import { nextTick, OnMounted, ref } from 'vue'
//props: {
 // msg: String
//}
const count = ref(0)
console.log(count.value)
console.log(count)
OnMounted(async()=>{
    await nextTick(()=> {
         
    })
    const someMethod= ()=> {
        count.value++
    }
})
//export default {
  //components: { MyButton, MyModal, LoginForm },
 // name: "HelloWorld",

  //props: {
 //   msg: String,
 // },
 // data() {
 //   return {
 //     showModal: false,
 //     user: {
  //      name: "Olga",
  //      password: '123',
  //      isMe: false,
  //    },
 //   };
 // },
 // methods: {
  //  addLink() {
     
   //   this.user.link = "https://mts.ru";
   //   console.log(this.user);
  //  },
  //  removeLink() {
  //    delete this.user.link;
  //  },
  //  toggleModal() {
  //    this.showModal = !this.showModal;
  //  },
  //  firstEvent(data) {
  //    console.log("firstEvent", data);
  //  },
 //   secondEvent(data) {
  //    console.log("secondEvent", data);
  //  },
 // },
//};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
