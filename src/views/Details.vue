<template>
    <div class="container">
        <h4>User Page {{$route.params.userId}} </h4><br>
        <p>{{posts.title}}</p>
        <p>{{posts.body}}</p>
    </div>
</template>
<script>
    export default {
        name: 'details',
        data() {
            return {
                posts: {},
            }
        },
        created() {
            fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.userId}`)
                .then((res) => {
                    return res.json()
                })
                .then((data) => {
                    this.posts = data;
                })
        }
    }
</script>