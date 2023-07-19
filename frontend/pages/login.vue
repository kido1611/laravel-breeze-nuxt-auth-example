<script lang="ts" setup>
import {useAuthStore} from "~/stores/useAuthStore";

const form = ref({
    email: "test@example.com",
    password : "password"
})

const auth = useAuthStore()

async function handleLogin(){
    const { error } = await auth.login(form.value)

    console.log(error)
}
</script>

<template>
  <div>
    <form @submit.prevent="handleLogin">
        <div class="flex flex-col justify-start space-y-3">
            <label>
                Email
                <input class="px-3 py-2 border border-gray-300 rounded-md" type="email" v-model="form.email" />
            </label>
            <label>
                Password
                <input class="px-3 py-2 border border-gray-300 rounded-md" type="password" v-model="form.password" />
            </label>

            <button class="bg-red-500 text-white px-4 py-3"
                    type="submit">Login</button>
        </div>
    </form>
  </div>
</template>

<style scoped></style>
