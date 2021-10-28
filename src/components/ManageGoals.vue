<template>
    <base-card>

            <h2>Manage Goals</h2>
            <input type="text" ref="goal">
            <button @click="setGoal">Set Goal</button>
            <teleport to="body">
                <error-alert v-if="inputIsInvalid">
                    <h2>Input is invalid!</h2>
                    <p>Please enter at least 1 character</p>
                    <button @click="confirmDialog">Oke</button>
                </error-alert>
            </teleport>

    </base-card>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue'
export default {
    components: {
        ErrorAlert
    },
    data(){
        return {
            inputIsInvalid: false
        }
    },
    methods: {
        setGoal(){
            const eneteredValue = this.$refs.goal.value
            if(eneteredValue === ""){
                this.inputIsInvalid = true
            }
        },

        confirmDialog(){
            this.inputIsInvalid = false
        }
    }
}
</script>