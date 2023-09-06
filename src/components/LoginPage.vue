<template>
    <v-form ref="LoginForm" :lazy-validation="lazy">
        <v-card width="50%" height="100%">
        <v-card-title>เข้าสู่ระบบ</v-card-title>
        <v-card-text>
        <!-- username -->
        <v-row dense>
            <v-col cols="12" align="start">
                <span>ชื่อผู้ใช้งาน: </span><br/>
                <v-text-field v-model="username" rounded outlind dense :rules="Rules.usernameRules"></v-text-field>
            </v-col>
            </v-row>
            <!-- password -->
            <v-row dense>
                <v-col cols="12" align="start">
                    <span>รหัสผ่าน:</span><br/>
                    <v-text-field v-model="password" rounded outline dense :rules="Rules.passwordRules"></v-text-field>
                </v-col>
            </v-row>
        </v-card-text>
        <v-card-actions>
            <v-btn block rounded color="17B169" class="white--text" @click="login()">เข้าสู่ระบบ</v-btn>
        </v-card-actions>
     </v-card>
    </v-form>
</template>
<script>
export default {
    data () {
        return {
            lazy: false,
            username: '',
            password: '',
            Rules:{
                usernameRules:[
                    v => !!v || 'กรุณากรอกชื่อผู้ใช้งาน'
                ],
                passwordRules:[
                    v =>!!v || 'กรุณากรอกรหัสผ่าน'
                ]

            }
        }

    },
    methods:{
        login () {
            if (this.$refs.LoginForm.validate(true)){
                localStorage.setItem('username', this.username)
                this.$EventBus.$emit('getUsername')
                this.$EventBus.$emit('checkLoign')
                this.$route.push({ path: '/' }).catch(() => {})
            }

        }

    }
}
</script>

<style>

</style>