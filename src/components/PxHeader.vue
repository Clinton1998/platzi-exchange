<template>
    <header class="shadow w-screen">
        <nav>
            <nav class="flex items-center justify-between flex-wrap bg-green-400 p-6">
                <div class="flex items-center flex-shrink-0 text-white mr-6">
                    <px-icon class="mr-3"></px-icon>
                    <router-link class="font-semibold text-xl tracking-tight" v-bind:to="{name: 'home'}">Platzi Exchange</router-link>
                </div>
                <div class="hidden sm:block w-full block flex-grow lg:flex lg:items-center lg:w-auto">
                    <div class="text-sm lg:flex-grow">
                        <router-link
                        class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white mr-4" v-for="l in links" 
                        v-bind:key="l.title" 
                        v-bind:to="l.to"
                        >{{ l.title }}</router-link>
                    </div>
                </div>
            </nav>
        </nav>
    </header>
</template>
<script>
import PxIcon from '@/components/PxIcon.vue'

export default {
    name: 'PxHeader',
    props: {
        links: {
            type: Array,
            default:() => []
        }
    },
    components: {
        PxIcon
    },
    created(){
        console.log('Created')
    },
    mounted(){
        console.log('Mounted')
    }
}
</script>