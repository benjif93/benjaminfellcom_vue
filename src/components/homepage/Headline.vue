<template>
  <div class="homepage-headline">
      <h2>{{ headline_content }}</h2>
  </div>
</template>


<script>
    import { butter } from '@/buttercms'
    export default {
        name: 'homepage-headline',
        data() {
            return {
                headline_content: ''
            }
        },
        methods: {
            getHeadline() {
                butter.content.retrieve(['benjaminfell_homepage_headline'])
                  .then((res) => {
                    console.log(res.data.data)
                    this.headline_content = res.data.data.benjaminfell_homepage_headline
                  })
            }
        },
        created() {
            this.getHeadline()
        }
    }
</script>