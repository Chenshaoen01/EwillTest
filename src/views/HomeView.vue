<template>
  <homePageHeader></homePageHeader>
  <homePageForm></homePageForm>
  <medalSection></medalSection>
  <boothArea></boothArea>
</template>

<script>
import homePageHeader from '../components/HomePageHeader.vue';
import homePageForm from '../components/HomePageFormTest.vue';
import medalSection from '../components/MedalSection.vue';
import boothArea from '../components/BoothArea.vue';

export default {
  name: 'HomeView',
  components: {
    homePageHeader, homePageForm, medalSection, boothArea,
  },
};
</script>
