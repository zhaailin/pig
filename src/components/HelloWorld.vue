<template>
  <div style="width:100%;height:100%">
    <div class="pig">
      <div class="pig-title">
        <h1 style="color:#fff;font-size:100px">我的小猪猪</h1>
      </div>
      <div class="pig-body">
        <a-card title="七夕快乐" style="width: 300px">
          <a @click="open" slot="extra"
            ><img src="../assets/猪肉包.png" style="width:2em"
          /></a>
          <p style="color:green">{{ time }}</p>
          <p style="color:orange">金风玉露一相逢</p>
          <p style="color:orange">便胜却人间无数</p>
        </a-card>
      </div>
    </div>
    <a-modal :visible="visible" @ok="handleOk" @cancel="handleCancel">
      <div
        style="width:100%;height:100%;display:flex;  justify-content: center;
  align-items: center"
      >
        <div style="color:pink;">
          你就是小猪猪
        </div>
        <a-popconfirm
          title="关不掉吧?说你是小猪猪还不信，承认自己是小猪猪"
          ok-text="我是小猪猪"
          cancel-text="我不是小猪猪"
          :visible="visible2"
          @confirm="confirm"
          @cancel="cancel"
        >
        </a-popconfirm>
        <a-popconfirm
          title="哈哈哈，点确定，关不掉,臭猪猪"
          ok-text="Yes"
          cancel-text="No"
          :visible="visible3"
          @confirm="confirm2"
          @cancel="cancel2"
        >
        </a-popconfirm>
      </div>
      <div><img src="../assets/a.jpeg" alt=""></div>
    </a-modal>
  </div>
</template>

<script>
import dayjs from "dayjs";
export default {
  data() {
    return {
      content: "",
      time: dayjs(new Date()).format("YYYY-MM-DD HH:mm"),
      visible: false,
      visible2: false,
      visible3: false
    };
  },
  created() {},
  methods: {
    open() {
      this.visible = true;
    },
    handleOk() {
      this.visible3 = true
    },
    handleCancel() {
      this.visible2 = true;
    },
    confirm() {
     this.visible = false
     this.visible2 = false
    },
    confirm2() {
     this.visible3 = false
    },
    cancel2() {
      this.visible3 = false
    }
  }
};
</script>

<style scoped>
.pig {
  width: 100%;
  height: 100%;
  background: url(../assets/pig.jpg);
}
.pig-title {
  height: 300px;
}
.pig-body {
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
