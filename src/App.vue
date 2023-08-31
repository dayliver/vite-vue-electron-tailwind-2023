<script setup>
const ping = async () => {
    const response = await window.electron.ping();
    console.log(response); // prints out 'pong'
}

const powers = [
    { label: 'Vite', url: 'https://vitejs.dev/' },
    { label: 'Vue', url: 'https://vuejs.org/' },
    { label: 'Electron', url: 'https://www.electronjs.org/' },
    { label: 'TailwindCSS', url: 'https://tailwindcss.com/' }
];
</script>

<template>
    <div class="w-full h-screen flex flex-col">
        <div class="m-auto flex flex-col gap-8 text-center">
            <div>This template is powered by:</div>
            <div class="flex gap-8">
                <a
                    v-for="power of powers"
                    :href="power.url"
                    class="text-2xl"
                >{{ power.label }}</a>
            </div>
        </div>
        <div class="m-auto flex flex-col gap-4 text-center">
            <div>Click the button to communicate with Electron!</div>
            <button class="my-button" @click="ping">Ping</button>
            <div>The result will be displayed in console.</div>
        </div>
    </div>
</template>

<style scoped>
.my-button {
    @apply rounded-xl border py-2 font-bold;
}
</style>
