<template>
    <div class="modal">
        <h3 id="header" v-if="uiState==='Won'">
            Congratulations! You've won the game! 
        </h3>
        <h3 v-else id="header">
            Oops! You've lost the game!
        </h3>
        <slot></slot>
        <button @click="updateUIState">Let's play again</button>
    </div>
    
</template>

<script>
import { mapState } from 'vuex'
    export default {
        computed: {
            ...mapState(['uiState'])
        },
        methods: {
            updateUIState(){
                this.$store.commit('startAgain', 'start');
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>