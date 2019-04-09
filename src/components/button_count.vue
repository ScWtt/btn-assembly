<template>
  <div>
    <button
      class="submit_btn"
      v-on:click="submitClick"
      :disabled="dis"
      :style="{backgroundColor:bgcolor,cursor:curstyle}"
    >
      <img class="loading-img" :src="btnImg" alt v-if="isShow">
      <slot></slot>
    </button>
  </div>
</template>
<script type="text/ecmascript-6">
export default {
  props: {
    isShow: {
      type: Boolean,
      default: false
    },
    dis: {
      type: Boolean,
      default: false
    },
    bgcolor: {
      type: "",
      default: "green"
    }
  },
  data() {
    return {
      btnImg: "../../static/images/loading.png"
    };
  },
  methods: {
    submitClick() {
      this.$emit("changeshow");
    }
  },
   computed:{
    curstyle:function(){
      return this.dis?"not-allowed":"pointer"
    }
  }
};
</script>
<style scope>
.submit_btn {
  line-height: 30px;
  height: 30px;
  outline: none;
  border: 1px solid #000;
  border-radius: 5px;
}
.loading-img {
  padding-right: 5px;
  height: 20px;
  width: 20px;
}
</style>
