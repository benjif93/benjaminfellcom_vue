<template>
    <div id="Copyright">
        <p>© {{ current_year }} • {{ footer_headline }}</p>
    </div>
</template>

<script>
    import { butter } from '@/buttercms'
    export default {
        name: 'FooterCopyright',
        data() {
            return {
                current_year: new Date(),
                footer_headline: ''
            }
        },
        methods: {
            getCopyright() {
                butter.content.retrieve(['benjaminfell_footer'])
                  .then((res) => {
                      console.log(res.data.data)
                      this.footer_headline = res.data.data.benjaminfell_footer
                  })
            },
            getCurrentYear() {
                this.current_year = (new Date()).getFullYear()
            }
        },
        created() {
            this.getCopyright(),
            this.getCurrentYear()
        }
    }
</script>