<template>
  <app-layout title="Curriculum vitae">
    <template #header>
      <h2 class="h4 font-weight-bold">
        Profile
      </h2>
    </template>

    <div v-if="$page.props.jetstream.canUpdateProfileInformation">
      <update-profile-information-form :user="$page.props.user" />

      <jet-section-border />
    </div>
    
    {{users}}
  </app-layout>
</template>

<script>
import { defineComponent } from 'vue'
import AppLayout from '@/Layouts/AppLayout.vue'

import JetSectionBorder from '@/Jetstream/SectionBorder.vue'

import UpdateProfileInformationForm from '@/Pages/Profile/Partials/UpdateProfileInformationForm.vue'

export default defineComponent({
  props: ['sessions', 'users'],

  components: {
    AppLayout,
    JetSectionBorder,
    UpdateProfileInformationForm,
  },
})
</script>
