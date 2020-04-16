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
      // sort by group meta
      // field.value[]  .custom_properties.group
      console.log(this.field.value);
      console.log(
        this.field.value.sort((a, b) => {
          if (a.custom_properties.group && b.custom_properties.group) {
            console.log(a.custom_properties.group);
            console.log(b.custom_properties.group);
          }
        })
      );
      return this.field.value;
    }
  },
  props: ["resource", "resourceName", "resourceId", "field"]
};
</script>
