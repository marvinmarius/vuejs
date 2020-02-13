<template>
<div>

    <form class="flex flex-column" @submit.prevent="submitComment">

        <textarea class="border rounded-circle " v-model="comment" placeholder ="content"></textarea>
        <input type="text" class="border rounded-circle " v-model="url" placeholder = "url">
        <p class=" text-red" v-if="errors.url"  >{{errors.url}}</p>
        <input type="text" class="border rounded-circle " v-model="name"  placeholder="name">
        <button type="submit">commenter</button>

    </form>
<div v-for="comment in comments">
    <div>{{comment.name}}</div>
    <div>{{comment.created_at}}</div>
    <div>{{comment.url}}</div>
    {{ comment.body}}

</div>
</div>
</template>

<script>
    export default {
     props:['dataComments'],
      methods:{
            submitComment(){
                axios.post('/comments' , {
                    content: this.comment,
                    name: this.name,
                    url: this.url,
                    created_at:this.created_at,
                }).then(({data}) =>{
                    this.comments.push({data})
                })
                .catch(error => {
                    console.dir(error.response.data.errors)
                })
            }
    },
    data(){
          return{
              url: '',
              name: '',
          comment: '',
              comments: this.dataComments,
            errors: {},

          }

    }
    }
</script>
