<template>
  <ParentLayout>
    <template #sidebar-top>
    <RebelAds />
    </template>
  </ParentLayout>
</template>

<script>
import ParentLayout from '@parent-theme/layouts/Layout.vue'
import RebelAds from '@theme/components/RebelAds.vue'

export default {
  name: 'Layout',

  components: {
    ParentLayout,
    RebelAds,
  }
}
</script>
