<template>
    <div>
        <moon-loader v-bind:loading="isLoading" v-bind:color="'#68d391'" v-bind:size="100"></moon-loader>
        <px-assets-table v-bind:assets="assets" v-if="!isLoading"></px-assets-table>
    </div>
</template>
<script>
import api from '@/api'
import PxAssetsTable from '@/components/PxAssetsTable.vue'
export default {
    name: 'Home',
    components:{
        PxAssetsTable
    },
    data(){
        return {
            isLoading: false,
            assets: []
        }
    },
    created(){
        this.isLoading = true
        api.getAssets()
        .then(assets => this.assets = assets)
        .finally(() => this.isLoading = false)
    }
}
</script>