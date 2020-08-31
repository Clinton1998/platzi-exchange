<template>
   <button class="bg-transparent bg-green-500 hover:bg-green-800 font-semibold text-white rounded" v-on:click="buttonClick">
		<beat-loader v-bind:loading="isLoading" v-bind:color="'#68d391'" v:bind:size="8"></beat-loader>
        <p v-show="!isLoading">
            <slot></slot>    
        </p>
   </button> 
</template>
<script>
export default {
    name: 'PxButton',
    props: {
		isLoading: {
			type: Boolean,
			default: false
		}
    },
    methods: {
        buttonClick(){
            this.$emit('custom-click')
        }
    }
}
</script>