<template>
    <div class="main-content">
        <div class="container">
            <h2 class="title is-2">{{ post.title }}</h2>
            <div v-html="post.content"></div>
            <br>
            <h4 class="title is-5 is-marginless">by <strong>{{ post.author }}</strong> at <strong>{{ post.published }}</strong></h4>
        </div>
    </div>
</template>

<script>
import posts from '~/posts.json'

export default {
    validate ({ params }) {
        return /^\d+$/.test(params.id)
    },
    async asyncData ({ params }, callback) {
        let post = posts.find(post => post.id === parseInt(params.id))
        console.log(123123)
        if (post) {
          await  callback(null, { post })
        } else {
          await callback({ statusCode: 404, message: 'Post not found' })
        }
    },
    head () {
        return {
            title: this.post.title,
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: this.post.summary
                }
            ]
        }
    }
}
</script>

<style>

</style>