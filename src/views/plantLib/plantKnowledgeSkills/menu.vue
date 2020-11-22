<template>
  <div class="skills_menu">
    <el-row :gutter="12">
      <el-col :span="8" v-for="item in menuList" :key="item.id" @click.native="linkToList(item)">
        <el-card shadow="hover">{{item.name}}</el-card>
      </el-col>
    </el-row>
    <!-- <el-row :gutter="12">
      <el-col :span="8">
        <el-card shadow="hover"> 寻找水源及消毒 </el-card>
      </el-col>
      <el-col :span="8">
        <el-card shadow="hover"> 取火 </el-card>
      </el-col>
      <el-col :span="8">
        <el-card shadow="hover"> 判断环境状况及驱逐虫兽 </el-card>
      </el-col>
    </el-row>
    <el-row :gutter="12">
      <el-col :span="8">
        <el-card shadow="hover"> 研制医疗器材代用品 </el-card>
      </el-col>
    </el-row> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
        menuList: [{
            name: '辨别地理方向',
            id: 'dili'
        }, {
            name: '预测天气',
            id: 'tianqi'
        }, {
            name: '海拔高度',
            id: 'haiba'
        }, {
            name: '寻找水源及消毒',
            id: 'shuiyuan'
        }, {
            name: '取火',
            id: 'quhuo'
        }, {
            name: '判断环境状况及驱逐虫兽',
            id: 'huanjing'
        }, {
            name: '研制医疗器材代用品',
            id: 'qixie'
        }]
    };
  },
  methods: {
      linkToList(item) {
          this.$router.push({
              path: `/plantlib/plantKnowledgeSkills/list/${item.id}`
          })
      }
  },
};
</script>

<style lang="scss">
.el-col {
  margin-bottom: 20px;
}
</style>