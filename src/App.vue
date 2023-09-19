<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        
      
      </div>

      <v-spacer></v-spacer>

      <v-btn text
               @click="goToManage()"
  >หน้าจัดการข้อมูล</v-btn>
    
    <v-btn text
               @click="goToLogin()"
  >เข้าสู่ระบบ</v-btn>
    
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
  methods: {
    goToLogin () {
      this.$router.push({path: '/login'}).catch(() =>{})
    },
    goToManage () {
      this.$router.push({path: '/manageTable'}).catch(() =>{})

    }
  }
}
</script>
