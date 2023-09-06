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

      <v-btn
        text
        @click="goToLogin()"
      >
        <span class="mr-2">เข้าสู่ระบบ</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
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
      this.$router.push('/login')
    }
  }
}
</script>
