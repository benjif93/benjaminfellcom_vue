<template>
    <div id="Skils">
        <h3>{{ section_title }}</h3>
        <ul>
            <li v-for="(skill, index) in skill_items" :key="index">{{ skill.skill }}</li>
        </ul>
    </div>
</template>

<script>
    import { butter } from '@/buttercms'
    export default {
        name: 'Skills',
        data() {
            return {
                section_title: 'Skills',
                skill_items: []
            }
        },
        methods: {
            getSkills() {
                butter.content.retrieve(['benjaminfell_skills'])
                  .then((res) => {
                      console.log(res.data.data)
                      this.skill_items = res.data.data.benjaminfell_skills
                  })
            }
        },
        created() {
            this.getSkills()
        }
    }
</script>