<template>
    <div class="bgc center">
        <div class="container">
            <div class="header">
            <h1><span class="l">L</span>OGIN</h1>
            </div>
            <form>
            <label for="uname">Username</label>
            <input v-model="userBe.email" type="text" class="inp" name="uname" required>
            <label for="psw">Password</label>
            <input v-model="userBe.password" type="password" class="inp" name="psw" required>
            <button v-on:click.prevent="login" type="submit">Enter</button>
            </form>
            <div class="signup">
            <b>Don't have account?</b>
            <a href="#">Sign up</a>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props : ['userBe'],
        methods : {
            login() {
                this.$emit('se-connecter', this.userBe)
            }
        }
    }
</script>
<style lang="scss" scoped>
    body {
        font-family: monospace !important;
        
    }
    .container {
    background-color: #fff;
    padding: 25px;
    margin: 50px auto;
    width: 275px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .header {
    text-align: center;
    margin-bottom: 20px;
    }
    .header h1 {
    font-size: 24px;
    color: #000;
    }
    h1 > .l {
    font-size: 30px;
    color: #8c0000;
    }
    label {
    font-weight: 700;
    font-size: 16px;
    }
    .inp {
    font-weight: 500;
    width: 100%;
    padding: 2.5px 3.75px;
    margin: 8px 0;
    display: inline-block;
    border: 2px solid #132;
    border-top: 0;
    border-left: 0;
    border-right: 0;
    }
    .inp,
    .inp:focus {
    outline: none;
    }
    button {
    background-color: #8c0000;
    color: white;
    padding: 12px 20px;
    margin: 8px 0;
    width: 100%;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    opacity: 0.925;
    }
    button:hover {
    opacity: 1;
    }
    .signup {
    width: 250px;
    padding: 0 7.5px;
    text-align: center;
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    }
    .signup a {
    font-weight: 800;
    color: #8c0000;
    text-decoration: none;
    }
    .signup a:hover {
    text-decoration: underline;
    }

</style>