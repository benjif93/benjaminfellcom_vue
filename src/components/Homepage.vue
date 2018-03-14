<template>
  <div id="Homepage">
    <homepage-headline></homepage-headline>
    <homepage-employment></homepage-employment>
    <homepage-skills></homepage-skills>
  </div>
</template>


<script>
    import HomepageHeadline from '@/components/homepage/Headline'
    import HomepageEmployment from '@/components/homepage/Employment'
    import HomepageSkills from '@/components/homepage/Skills'
    export default {
        name: 'Homepage',
        components: {
            'homepage-headline': HomepageHeadline,
            'homepage-employment': HomepageEmployment,
            'homepage-skills': HomepageSkills
        }
    }
</script>