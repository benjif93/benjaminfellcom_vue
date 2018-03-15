<template>
    <div id="Copyright" class="footer__copyright">
        <div class="container">
            <div class="row">
                <div class="holder center-elem">
                    <p>© {{ current_year }} • {{ footer_headline }}</p>
                </div>
            </div>
        </div>
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
            this.getCopyright()
            this.getCurrentYear()
        }
    }
</script>

<style lang="scss" scoped>
    
    .holder {
        padding: 20px 3.5%;
    }

    @media (min-width: 768px) {
        .holder {
            width: 90vw;
            padding: 20px 0;
        }
    }

</style>
