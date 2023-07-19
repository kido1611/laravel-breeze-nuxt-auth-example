<script lang="ts" setup>
import {useAuthStore} from "~/stores/useAuthStore";

const auth = useAuthStore();
</script>

<template>
  <div class="max-w-xl px-6 flex flex-col space-y-8">
    <header class="py-4 -mx-4 flex flex-col">
        <ol class="flex flex-row items-center">
            <li>
                <NuxtLink active-class="bg-blue-100 text-blue-900 font-semibold"
                          class="hover:bg-gray-100 text-sm text-gray-700 px-4 py-3"
                          href="/">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink active-class="bg-blue-100 text-blue-900 font-semibold"
                          class="hover:bg-gray-100 text-sm text-gray-700 px-4 py-3"
                          href="/login">Login</NuxtLink>
            </li>
            <li>
                <NuxtLink active-class="bg-blue-100 text-blue-900 font-semibold"
                          class="hover:bg-gray-100 text-sm text-gray-700 px-4 py-3"
                          href="/register">Register</NuxtLink>
            </li>
            <li>
                <NuxtLink active-class="bg-blue-100 text-blue-900 font-semibold"
                          class="hover:bg-gray-100 text-sm text-gray-700 px-4 py-3"
                          href="/auth-only">Auth Only</NuxtLink>
            </li>
            <li>
                <NuxtLink active-class="bg-blue-100 text-blue-900 font-semibold"
                          class="hover:bg-gray-100 text-sm text-gray-700 px-4 py-3"
                          href="/guest-only">Guest Only</NuxtLink>
            </li>
        </ol>
        <div>
            <pre>{{ auth.user }}</pre>
        </div>
    </header>
    <slot />
  </div>
</template>

<style scoped></style>
