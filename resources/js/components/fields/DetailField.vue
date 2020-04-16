<template>
  <panel-item :field="field">
    <gallery slot="value" :value="field.value" :field="field" :multiple="field.multiple" />
  </panel-item>
</template>

<script>
import Gallery from "../Gallery";

export default {
  components: {
    Gallery
  },
  computed: {
    // orderedValue() {
    //   return this.field.value.sort((a, b) => {
    //     if (a.custom_properties.group && b.custom_properties.group) {
    //       if (a.custom_properties.group < b.custom_properties.group) {
    //         return -1;
    //       }
    //       if (a.custom_properties.group > b.custom_properties.group) {
    //         return 1;
    //       }
    //       return 0;
    //     } else {
    //       if (a.created_at < b.created_at) {
    //         return -1;
    //       }
    //       if (a.created_at > b.created_at) {
    //         return 1;
    //       }
    //       return 0;
    //     }
    //   });
    // }
  },
  props: ["resource", "resourceName", "resourceId", "field"]
};
</script>
