<template>
  <div>
    <b-container>
      <b-row>
        <b-col>
          <b-form inline>
            <label class="sr-only" for="inline-form-input-name">Email</label>
            <b-form-input v-model="email" id="inline-form-input-name" class="mb-2 mr-sm-2 mb-sm-0" placeholder="user@email.com"></b-form-input>
            <label class="sr-only" for="inline-form-input-username">Password</label>
            <b-form-input v-model="password" id="inline-form-input-username" type="password"></b-form-input>
            <b-button variant="primary" @click="register">Save</b-button>
          </b-form>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import AuthenticationServices from '@/services/AuthenticationService'

export default {
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    register: async function() {
      const response = await AuthenticationServices.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style>

</style>
