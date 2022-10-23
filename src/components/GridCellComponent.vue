<template>
  <div class="image-container" ref="imageContainer" @click="toggleView">
    <a :href="url" target="_blank" :alt="name">
      <img
        :src="require(`@/assets/images/${name}`)"
        :title="title"
        :alt="`${name}`"
        class="image"
        ref="image"
      />
    </a>
  </div>
</template>

<script>
export default {
  name: "GridCellComponent",
  props: {
    name: String,
    url: String,
    title: String,
  },
  methods: {
    toggleView() {
      const imageContainer = this.$refs.imageContainer;
      const image = this.$refs.image;

      if (imageContainer.classList.contains("full-image")) {
        imageContainer.classList.remove("full-image");
        image.classList.add("image");
      } else {
        imageContainer.classList.add("full-image");
        image.classList.remove("image");
      }
    },
  },
};
</script>

<style scoped>
img {
  display: block;
  width: 100%;
  transition: all 0.3s ease-in-out;
}

.image:hover {
  transform: scale(1.2);
  transition: all 0.5s ease;
}

.full-image {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 99;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 100vw;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  transition: all 0.5s ease;
}
</style>
