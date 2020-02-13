<template>

                    <div class="card-body">
                        <input type="text">
                    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        },
        data(){
            return {
                'name': 'Marius'
            }
        },
    }
</script>
