<template>
  <div >
    <wkProgress percent="50"
                    wk_height="50"
                    wk_radius="50"
                    wk_width="500"
                    wk_text_color="red"
                    wk_color="blue"
                    wk_bgColor="green"
                    wk_font_size="40"
                    wk_font_weight="60"
                    wk_text="test" @wk_click="click">
                    </wkProgress>
  </div>
</template>


<script>
/* eslint-disable */
import wkProgress from "./wk-progress.vue";
export default {
  components: { wkProgress },
  methods: {
    click() {
      console.log("click");
    }
  }
};
</script>

<style scoped>
</style>