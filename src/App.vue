<template>
  <div>
    <div v-if="!loggedIn">
        <div class="row">
            <div class="col-6 offset-3 mt-5">
                <div class="card">
                    <div class="card-header">
                        <h2>Login Form</h2>
                    </div>
                    <div class="card-body">
                        <form @submit.prevent="login">
                            <div class="form-group">
                                <label for="username">Username/Email:</label>
                                <input type="text" class="form-control" id="username" v-model="usernameOrEmail" required/>
                            </div>
                            <div class="form-group">
                                <label for="password">Password:</label>
                                <input type="password" class="form-control" id="password" v-model="password" required/>
                            </div>
                            <div class="form-group mt-2">
                                <button type="submit" class="btn btn-primary">Login</button>
                            </div>
                        </form>
                    </div>
                </div>


            </div>
        </div>

    </div>

    <div v-if="loggedIn">
        <div class="row">
            <div class="mt-5 col-6 offset-3">
                <div class="card">
                    <div class="card-header">
                        <h2>Welcome to the Dashboard</h2>
                    </div>
                    <div class="card-body">
                        <p>Username/Email: {{ usernameOrEmail }}</p>
                    </div>
                </div>
            </div>
        </div>



    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue';

const usernameOrEmail = ref('')
const password = ref('')
const loggedIn = ref(false)
const login = () => {
  if (usernameOrEmail.value == '') {
    alert('Username/Email is required !')
  }
  if (password.value == '') {
    alert('Password is required !')
  }
  if (usernameOrEmail.value && password.value) {
    loggedIn.value = true;
  }
}
</script>
