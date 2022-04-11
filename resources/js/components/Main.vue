<template>
    <div class="container">
            <h1>Elenco dei Post</h1>
        <div class="row justify-content-center">
            <div v-for="post in posts" :key="post.id" class="col">
                <div class="card">
                    <div class="card-header">{{post.title}}</div>
                    <div class="card-body">
                        {{post.content}}
                        <a class="btn btn-primary" href="#">Vedi Post</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
       name: 'Main',
       components: { 

       },
       data() {
           return{
            posts : [],
               
           }
       },
       methods: {
           getPosts(){
            // Tutte le rotte che sono dentro api.php iniziano per /api 
            axios.get('/api/posts')
            .then((response) => {
                // handle success
                this.posts = response.data.results;
            });
           }
       },
       mounted(){
           this.getPosts();
       }
    };
</script>
