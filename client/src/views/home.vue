<template>
  <div v-for="img in imgs"><img :src="img" alt="" /></div>
</template>

<script>
export default {
  data() {
    return {
      imgs: ["/src/assets/img_4k/1.jpg"],
     
    };
  },
  components: {},
  mounted() {},
  methods: {},
};
</script>
