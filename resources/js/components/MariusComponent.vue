<template>

    <div class="card-body">
        <input :type="show ? 'text': 'password'" >
        <input type="checkbox" v-model="show">
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        },
        data(){
            return {
                'name': 'Marius',
                'show': 'true'
            }
        },
    }
</script>
