<template>
   <div>
  <v-btn color="primary"  elevation="3" large class ="mt-4"  >ปุ่มกด </v-btn>
  <div class="text-center">
    <v-btn
      class="mx-2"
      fab
      dark
      small
      color="primary"
    >
    
      <v-icon dark>
        mdi-minus
      </v-icon>
    </v-btn>

    <v-btn
      class="mx-2"
      fab
      dark
      small
      color="pink"
    >
      <v-icon dark>
        mdi-heart
      </v-icon>
    </v-btn>

    <v-btn
      class="mx-2"
      fab
      dark
      color="indigo"
    >
      <v-icon dark>
        mdi-plus
      </v-icon>
    </v-btn>

    <v-btn
      class="mx-2"
      fab
      dark
      color="teal"
    >
      <v-icon dark>
        mdi-format-list-bulleted-square
      </v-icon>
    </v-btn>

    <v-btn
      class="mx-2"
      fab
      dark
      large
      color="cyan"
    >
      <v-icon dark>
        mdi-pencil
      </v-icon>
    </v-btn>

    <v-btn
      class="mx-2"
      fab
      dark
      large
      color="purple"
    >
      <v-icon dark>
        mdi-android
      </v-icon>
    </v-btn>
    
  </div>

  <hello-world />
  
</div> 

</template>

<script>
import HelloWorld from '../components/HelloWorld'

export default {
  name: 'Home',

  components: {
    HelloWorld
  }
}
</script>
