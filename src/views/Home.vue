<template>
  <div class="home">
    <div v-if="!navbar">
       <Header></Header>
   </div>
   <div v-if="navbar">
       <HeaderSignIn></HeaderSignIn>
     </div>
    
    <Contents></Contents>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import HeaderSignIn from '@/components/HeaderSignIn.vue'
import Contents from '@/components/Contents.vue'
// import firebase from "firebase";

export default {
  components: { Header,Contents,HeaderSignIn},
  name: 'Home',
   data() {
    return {
      navbar: null,
    };
  },
  //  created() {
  //  this.$nextTick(function() {
  //     firebase.auth().onAuthStateChanged(function(user) {
  //       if (user) {
  //         console.log('ログイン中',user)
  //         this.navbar = true;
  //       } else {
  //         console.log('ログインアウト中')
  //         this.navbar = false;
  //         console.log(this.navbar)
  //       }
  //     });
  //   });
  //  }
}
</script>
