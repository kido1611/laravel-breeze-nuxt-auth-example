<script lang="ts" setup>
import {useAuthStore} from "~/stores/useAuthStore";

const form = ref({
    name: '',
    email: "",
    password : "",
    password_confirmation: ""
})

const auth = useAuthStore()

async function handleRegister() {
    const { error } = await auth.register(form.value)
    if(!error.value) {
        navigateTo("/")
    }
}
</script>

<template>
    <div>
        <form @submit.prevent="handleRegister">
            <div class="flex flex-col justify-start space-y-3">
                <label>
                    Nama
                    <input required class="px-3 py-2 border border-gray-300 rounded-md" type="text" v-model="form.name" />
                </label>
                <label>
                    Email
                    <input required class="px-3 py-2 border border-gray-300 rounded-md" type="email" v-model="form.email" />
                </label>
                <label>
                    Password
                    <input required class="px-3 py-2 border border-gray-300 rounded-md" type="password" v-model="form.password" />
                </label>
                <label>
                    Password (Ulang)
                    <input required class="px-3 py-2 border border-gray-300 rounded-md" type="password" v-model="form.password_confirmation" />
                </label>

                <button class="bg-red-500 text-white px-4 py-3"
                        type="submit">Daftar</button>
            </div>
        </form>
    </div>
</template>

<style scoped></style>
