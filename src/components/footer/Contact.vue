<template>
  <div id="FooterContact">
      <h2>{{ section_title }}</h2>
      <div>
          <ul>
              <li v-for='(contact, index) in contact_items' :key='index'>
                  <span>{{ contact.platform }}:</span> <a :href="contact.link_url">{{ contact.link_text }}</a>
              </li>
          </ul>
      </div>
  </div>
</template>

<script>
    import { butter } from '@/buttercms'
    export default {
        name: 'FooterContact',
        data() {
            return {
                section_title: 'Contact Me',
                contact_items: ''
            }
        },
        methods: {
            getContact() {
                butter.content.retrieve(['benjaminfell_contact'])
                  .then((res) => {
                      console.log(res.data.data)
                      this.contact_items = res.data.data.benjaminfell_contact
                  })
            }
        },
        created() {
            this.getContact()
        }
    }
</script>