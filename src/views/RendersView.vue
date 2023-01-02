<template>
  <GridComponent :cells="cells" />
</template>

<script>
import GridComponent from "@/components/GridComponent.vue";

export default {
  name: "RendersView",
  components: {
    GridComponent,
  },
  data() {
    return {
      cells: [
        { name: "headphone.png" },
        { name: "flower_closeup.png" },
        { name: "ships.png" },
        { name: "cnc_machine.png" },
        { name: "teapot.png" },
        { name: "big_daddy_eevee_final.png" },
        { name: "spicy_314_front.png" },
        { name: "cell_shaded.png" },
      ],
    };
  },
};
</script>

<style scoped></style>
