<template>
  <div v-if="user.isConnected">
    <h1>count : {{ count }}</h1>
    <h2>{{ count45 }}</h2>
    <h1>{{ count45_2() }}</h1>
    <div v-html="paragraph">
    </div>
    <input v-model="pas" type="number" name="" id="">
    <button v-on:click="increment">increment count</button>
    <button v-on:click="decrement">decrement count</button>
  </div>
  <form-be @se-connecter="login" v-else :user-be="user"/>
</template>
<script>
  import Form from './components/FormLogin.vue';
  export default {
    components : {
      FormBe : Form
    },
    data() {
      return {
        user : {
          email : '',
          password : '',
          isConnected : false
        },
        userExact : {
          email : 'test@gmail.com',
          password : 'password',
        },
        count : 0,
        paragraph :`
          <p class="tetet">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quaerat debitis tempora, rem unde repellat aspernatur natus sed molestias vel et eveniet minus alias
            quasi, dolorum sit expedita dolorem eum qui!
          </p>
        `, 
        pas : 52
      }
    },
    computed : {
      count45() {
        return this.count + 45;
      }
    },
    watch : {
      count(newValue, lastValue) {
        alert('last :' + lastValue + ' next : ' + newValue);
      }
    },
    methods : {
      count45_2() {
        return this.count + 45;
      },
      increment() {
        
        this.count = this.count + this.pas;
      },
      decrement() {
        this.count = this.count - this.pas;
      },
      login(params) {
        console.log(params)
      }
    }
  }
</script>