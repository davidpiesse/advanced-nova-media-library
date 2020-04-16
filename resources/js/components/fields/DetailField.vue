<template>
  <panel-item :field="field">
    <gallery slot="value" :value="orderedValue" :field="field" :multiple="field.multiple" />
  </panel-item>
</template>

<script>
import Gallery from "../Gallery";

export default {
  components: {
    Gallery
  },
  computed: {
    orderedValue() {
      console.log(this.field.value);
      // Todo get this to sort by the group where possible
      return this.field.value.sort((a, b) => {
        if (a.custom_properties.group && b.custom_properties.group) {
          if (a.custom_properties.group < b.custom_properties.group) {
            return -1;
          }
          if (a.custom_properties.group > b.custom_properties.group) {
            return 1;
          }
          return 0;
        } else {
          if (a.file_name < b.file_name) {
            return -1;
          }
          if (a.file_name > b.file_name) {
            return 1;
          }
          return 0;
        }
      });
    }
  },
  props: ["resource", "resourceName", "resourceId", "field"]
};
</script>
