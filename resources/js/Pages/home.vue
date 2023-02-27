<template>
<v-theme-provider theme="dark" with-background class="pa-5">
    <v-container>
    <v-row justify="space-around">
        <v-card width="400" height="520" class="mt-2">
        <v-img height="200" src="https://farmalkes.kemkes.go.id/wp-content/uploads/2020/11/kip.png" cover></v-img>
        <v-card-text>
            <div class="font-weight-bold ms-1 mb-2 text-center">
                <h2>Log in</h2>
            </div>
            <v-form>
                <v-text-field label="Username" v-model="form.username" :error-messages="errors.username"></v-text-field>
                <v-text-field label="Password" type="password" v-model="form.password" :error-messages="errors.password"
                ></v-text-field>
                    <v-btn block color="brown" @click="login">Log in</v-btn>
                <div class="mt-5">
                    <v-btn elevation="2" small x-small @click="register">Sign up</v-btn>
                </div>
            </v-form>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
</v-theme-provider>
</template>

<script>
import {router} from '@inertiajs/vue3'
export default {
props:{
    errors:Object
},
    data(){
        return{
            form:{
                username:"",
                password:"",
            }
        }
    },
    methods:{
        login(){
            router.post('/login', this.form)
        },
        register(){
            router.get('/register')
        }
    },


};
</script>

<style></style>
