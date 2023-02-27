<template>
<v-theme-provider theme="dark" with-background class="pa-5">
<v-app>
<v-main>
    <v-row justify="space-around">
    <v-card width="400" height="750" class="mt-5">
        <v-img height="200" src="https://farmalkes.kemkes.go.id/wp-content/uploads/2020/11/kip.png" cover></v-img>
        <v-card-text>
            <div class="font-weight-bold ms-1 mb-2 text-center">
                <h2>Sign up</h2>
            </div>
            <v-form>
            <v-text-field :error-messages="errors.nama" label="Nama Lengkap" v-model="form.nama"></v-text-field>
            <v-text-field :error-messages="errors.nik" label="NIK" v-model="form.nik"></v-text-field>
            <v-text-field :error-messages="errors.tlp" label="Nomor Handphone" v-model="form.tlp"></v-text-field>
            <v-text-field :error-messages="errors.username" label="Username" v-model="form.username"></v-text-field>
            <v-text-field :error-messages="errors.password"
            label="Password"
            type="password"
            v-model="form.password"
            ></v-text-field>
            <v-btn block color="brown" @click="register">Sign up</v-btn>
        <div class="mt-5">
            <v-btn elevation="2" small x-small @click="login">Log in</v-btn>
        </div>
            </v-form>
        </v-card-text>
    </v-card>
    </v-row>
</v-main>
</v-app>
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
            nama:"",
            nik:"",
            hp:"",
            username:"",
            password:"",
        }
    }

},
methods:{
        login(){
            router.get('/')
        },
        register(){
            router.post('register', this.form)
        }
    }
}
</script>

<style>

</style>
