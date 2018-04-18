<template>
<div class="tab-box">
  <div class="tab-header">
    <el-row>
      <el-col :span="24">
        <el-tag
          class="tagitem"
          v-for="tag in tags"
          :key="tag.name"
          :type="tag.type">
          {{tag.name}}
        </el-tag>
      </el-col>
    </el-row>
  </div>
  <div class="tab-content">
    <div class="content-item" @click="showDialog"></div>
  </div>
  <el-dialog title="文件详情" :visible.sync="dialogTableVisible">
    <div class='video-box'>
      <video controls="controls">
        <source src="http://www.zhangxinxu.com/study/media/cat.mp4" type="video/mp4">
      </video>
    </div>
    <div class="comment-box">
      <div class="item-box">
        <span class="user-img"></span>
        <span class="user-box">
          <span class="user-input">
            <textarea name="" id="" cols="60" rows="3"></textarea>
          </span>
          <el-button class="submitbtn" size="mini" round type="primary">主要按钮</el-button>
        </span>
      </div>
      <div class="item-box">
        <span class="user-img"></span>
        <span class="user-box">
          <p class="user-info">
            <span class="name">name</span>
            <span class="time">2018/04/18</span>
          </p>
          <p class="comments">haoa very good!</p>
        </span>
      </div>
      <div class="item-box">
        <span class="user-img"></span>
        <span class="user-box">
          <p class="user-info">
            <span class="name">name</span>
            <span class="time">2018/04/18</span>
          </p>
          <p class="comments">haoa very good!</p>
        </span>
      </div>
    </div>
  </el-dialog>
</div>
</template>
<script>
export default {
  data() {
    return {
      tags: [
        { name: "标签一", type: "" },
        { name: "标签二", type: "success" },
        { name: "标签三", type: "info" },
        { name: "标签四", type: "warning" },
        { name: "标签五", type: "danger" }
      ],
      dialogTableVisible: false
    };
  },
  methods: {
    showDialog() {
      this.dialogTableVisible = true;
    }
  }
};
</script>

<style lang="less">
.tagitem {
  margin-right: 15px;
  cursor: pointer;
}
.tab-content {
  // width: 500px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  .content-item {
    cursor: pointer;
    width: 100px;
    height: 100px;
    margin-right: 18px;
    margin-top: 18px;
    background-color: antiquewhite;
  }
}
.video-box {
  height: 300px;
  width: 300px;
  margin: 0 auto;
  // background-color: aquamarine;
  video {
    height: 100%;
    width: 100%;
  }
}
.comment-box {
  .item-box {
    margin-top: 20px;
  }
  margin-top: 20px;
  span {
    display: inline-block;
  }
  .user-img {
    vertical-align: -10px;
    width: 50px;
    height: 50px;
    background-color: antiquewhite;
    border-radius: 25px;
  }
  .user-box {
    margin-left: 30px;
    .user-input {
      vertical-align: -10px;
    }
    .submitbtn {
      vertical-align: 13px;
    }
    p {
      margin: 0;
    }
    .name {
      font-weight: 600;
      color: black;
      padding-right: 20px;
    }
  }
}
</style>