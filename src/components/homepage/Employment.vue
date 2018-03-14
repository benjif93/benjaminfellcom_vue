<template>
    <div id="employment">
        <h2>{{ section_title }}</h2>
        <div class="employment-list">
            <div v-for="(employer, index) in employment_items" :key="index">
                <div class="employment-list__info">
                    <div class="employment-list__location"><h3>{{ employer.organisation_name }}</h3>, <h4>{{ employer.organistion_base }}</h4></div>
                    <div class="employment-list__date"><time>{{ employer.date_from }}</time> - <time>{{ employer.date_to }}</time></div>
                    <div class="employment-list__role">{{ employer.role }}</div>
                </div>
                <div id="employment-list__duties-and-achivements">
                    <h3>{{ section_subtitle }}</h3>
                    <div v-html="employer.duties_and_achivements"></div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
    import { butter } from '@/buttercms'
    export default {
        name: 'Employment',
        data() {
            return {
                section_title: 'Employment',
                section_subtitle: 'Dates and Achivements',
                employment_items: []
            }
        },
        methods: {
            getEmployment() {
                butter.content.retrieve(['benjaminfell_employment'])
                    .then((res) => {
                        console.log(res.data.data);
                        this.employment_items = res.data.data.benjaminfell_employment
                    })
            }
        },
        created() {
            this.getEmployment();
        }
    }
</script>