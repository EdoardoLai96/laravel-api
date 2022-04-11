<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <h1>Elenco dei Post</h1>
                <div class="card">
                    <div class="card-header">Componente Main</div>

                    <div class="card-body">
                        Main
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
       methods(){
           getPosts(){
            //    Tutte le rotte che sono dentro api.php iniziano per /api 
            axios.get('/api/posts')
            .then((response) => {
                // handle success
                console.log(response);
            });
           }
       },
    };
</script>
