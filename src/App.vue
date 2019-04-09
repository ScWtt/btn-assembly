<template>
  <div id="app">
    <button-count
      ref="countBtn"
      @changeshow="changeshow"
      :isShow="isShow"
      :dis="dis"
      bgcolor = '#345eee'
    >{{submitContent}}</button-count>
  </div>
</template>

<script>
import buttonCount from "../src/components/button_count";
export default {
  name: "App",
  data() {
    return {
      submitContent: "立即提交",
      isShow: false,
      dis: false
    };
  },
  methods: {
    changeshow() {
      this.isShow = !this.isShow;
      this.dis = !this.dis;
      if(this.dis){
        this.submitContent = "加载中";
      }
      let _this = this;
      var setStyle = setTimeout(function() {
        _this.isShow = false;
        _this.dis = false;
        _this.submitContent = "已经提交";
      }, 3000);
    }
  },
  components: {
    buttonCount
  }
};
</script>

<style>
</style>
