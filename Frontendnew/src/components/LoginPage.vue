<template>
    <v-form ref="loginForm" :lazy-validation="lazy">
        <v-card width="50%" height="100%">
        <v-card-title style="font-size: 30px !important;">เข้าสู่ระบบ</v-card-title>
        <v-card-text>
        <!-- username -->
        <v-row dense>
            <v-col cols="12" align="start">
                <span>ชื่อผู้ใช้งาน: </span><br/>
                <v-text-field counter="20" outlined label="ชื่อผู้ใช้งาน" v-model="username" rounded outlind dense :rules="Rules.usernameRules"></v-text-field>
            </v-col>
            </v-row>
            <!-- password -->
            <v-row dense>
                <v-col cols="12" align="start">
                    <span>รหัสผ่าน:</span><br/>
                    <v-text-field  :disabled="!valid" counter="20" outlined  label="รหัสผ่าน" v-model="password"  rounded outline dense  :type="show1 ? 'text' : 'password'" :rules="Rules.passwordRules"></v-text-field>
                </v-col>
            </v-row>
        </v-card-text>
        <v-card-actions>
            <v-btn block :disable="!valid"  color="#4DD0E1" class="white--text" @click="Login()">เข้าสู่ระบบ</v-btn>
        </v-card-actions>
     </v-card>
     
    </v-form>
</template>
<script>
export default {
    data () {
        return {
            lazy: false,
            valid: true,
            username: '',
            password: '',
            Rules:{
                usernameRules:[
                    v => !!v || 'กรุณากรอกชื่อผู้ใช้งาน',
                    v => (v && v.length <= 20) || 'กรุณากรอกชื่อผู้ใช้งานห้ามเกิน 20 ตัวอักษร'
                ],
            
                passwordRules:[
                    v =>!!v || 'กรุณากรอกรหัสผ่าน',
                    v => (v && v.length <= 20) || 'กรุณากรอกรหัสผ่านห้ามเกิน 20 ตัวอักษร'

                ]

            }
        }

    },
    methods:{
        Login () {
            if (this.$refs.loginForm.validate(true)){
                localStorage.setItem('username', this.username)
                this.$EventBus.$emit('getUsername')
                this.$EventBus.$emit('checkLoign')
                this.$router.push({ path: '/' }).catch(() => {})
            }

        }

    }
}
</script>

<style>

</style>