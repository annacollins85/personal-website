<template>
  <slice-zone type="workshop_part" :uid="$route.params.uid" />
</template>

<script>
import SliceZone from 'vue-slicezone'

export default {
  components: {
    SliceZone,
  },
}
</script>
