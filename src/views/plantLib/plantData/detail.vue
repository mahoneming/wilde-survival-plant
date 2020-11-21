<template>
  <div class="plant_list_detail">
    <el-tabs v-model="activeName" type="card">
      <el-tab-pane label="信息" name="first">
        <div class="list">
          <div class="name"></div>
          <div class="value"></div>
        </div>
      </el-tab-pane>
      <el-tab-pane label="图片" name="second">
        <el-row :gutter="20">
          <el-col :span="6">
            <el-card class="box-card" header="手绘图">
              <el-image
                style="width: 100px; height: 100px"
                src='https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg'
                :preview-src-list="srcList"
                fit="fill"
              ></el-image>
            </el-card>
          </el-col>
        </el-row>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeName: "first",
      srcList: [
          'https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg',
        ]
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
  },
};
</script>

<style lang="scss">
.plant_list_detail {
  .list {
    display: flex;
  }
  .name {
    width: 200px;
  }
  .value {
    flex: 1;
  }
}
</style>