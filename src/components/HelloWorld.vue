<template>
<h1>{{ msg }}</h1>
<div class="flex flex-col items-center justify-center ">
  <form>
    <input v-model="input.email" name="email" type="text" placeholder="Email " class="text-sm text-gray-base w-full mr-3 py-5 px-4 h-2 border border-gray-200 rounded mb-2" />

    <input v-model="input.pwd" type="password" placeholder="Password" class="text-sm text-gray-base w-full mr-3 py-5 px-4 h-2 border border-gray-200 rounded mb-2" />
  
    <button @click="login" type="submit" class="w-full text-white bg-blue-700 hover:bg-blue-800 focus:outline-none focus:ring-4 focus:ring-blue-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"> Login </button>
  </form>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {reactive} from 'vue';
import {useRouter} from 'vue-router';
import { useUserStore } from "../store/user";
export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  setup(){
  const router = useRouter();
const store=useUserStore();

const input = reactive({
  email:'',
  pwd:'' 
});

const login=()=> {
 if(input.email != store.user.email || input.pwd != store.user.pwd) {
                        alert("The username and / or password is incorrect");
                    }
 else {
               alert("Login Successful");
                 router.replace({name:"about"});
                }

            }
            return {input,login};
  },
  });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
