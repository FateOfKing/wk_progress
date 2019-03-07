<template>
  <div class="wk-div" :style="wk_style">
    <div class="wk-mask-div-father" :style="wk_mask_father_style">
      <div class="wk-mask-div" :style="wk_mask_style"></div>
    </div>
    <div  class="wk-show-div" :style="wk_show_style" @click="action">
      <text class="wk-text" :style="wk_text_style">{{wk_text}}</text>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  props: {
    wk_color: {
      type: String,
      default: "lightblue"
    },
    wk_bgColor: {
      type: String,
      default: "#c3c3c3"
    },
    percent: {
      type: Number,
      default: 50
    },
    wk_radius: {
      type: Number,
      default: 5
    },
    wk_width: {
      type: Number,
      default: 600
    },
    wk_height: {
      type: Number,
      default: 10
    },
    wk_font_weight: {
      type: Number,
      default: 500
    },
    wk_font_size: {
      type: Number,
      default: 23
    },
    wk_text_color: {
      type: String,
      default: "#ffffff"
    },
    wk_text: {
      type: String,
      default: ""
    }
  },
  computed: {
    wk_style() {
      return {
        width: this.wk_width + "px",
        height: this.wk_height + "px"
      };
    },

    wk_mask_father_style() {
      return {
        backgroundColor: this.wk_bgColor,
        borderRadius: this.wk_radius + "px",
        height: this.wk_height + "px"
      };
    },
    wk_mask_style() {
      return {
        width: this.wk_width * this.percent / 100 + "px",
        height: this.wk_height + "px",
        backgroundColor: this.wk_color
      };
    },
    wk_show_style() {
      return {
        width: this.wk_width + "px",
        height: this.wk_height + "px"
      };
    },
    wk_text_style() {
      return {
        height: this.wk_height + "px",
        color: this.wk_text_color,
        fontSize: this.wk_font_size + "px",
        fontWeight: this.wk_font_weight,
        lineHeight: this.wk_height + "px"
      };
    }
  },
  data() {
    return {};
  },
  methods: {
    action() {
      this.$emit("wk_click");
    }
  }
};
</script>

<style scoped>
.wk-div {
  flex: 1;
}

.wk-mask-div {
  position: absolute;
  top: 0;
  left: 0px;
}

.progress {
  flex: 1;
}

.wk-show-div {
  position: absolute;
  left: 0px;
  top: 0px;
  flex: 1;
}
.wk-mask-div-father {
  overflow: hidden;
}

.wk-text {
  flex: 1;
  text-align: center;
}
</style>
