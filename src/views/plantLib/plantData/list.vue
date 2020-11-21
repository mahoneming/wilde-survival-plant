<template>
  <div class="plant_list">
    <div class="plant_list_form">
      <el-form :inline="true" :model="formInline" class="demo-form-inline">
        <el-form-item label="">
          <el-input v-model="formInline.user" placeholder="名称"></el-input>
        </el-form-item>
        <el-form-item label="">
          <el-select v-model="formInline.region" placeholder="区域">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="">
          <el-select v-model="formInline.region" placeholder="军事医学应用">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="">
          <el-select v-model="formInline.region" placeholder="传统功效">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="">
          <el-select v-model="formInline.region" placeholder="疾病名称">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="">
          <el-select v-model="formInline.region" placeholder="军事野外应用">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">查询</el-button>
          <el-button @click="onSubmit">新增</el-button>
          <el-button @click="onSubmit">导入</el-button>
        </el-form-item>
      </el-form>
    </div>
    <div class="plant_list_table">
      <el-table :data="tableData" border style="width: 100%">
        <el-table-column type="index" width="50"></el-table-column>
        <el-table-column prop="date" label="中文名称"> </el-table-column>
        <el-table-column prop="name" label="拉丁学名"> </el-table-column>
        <el-table-column prop="province" label="别名"> </el-table-column>
        <el-table-column prop="city" label="药材名"> </el-table-column>
        <el-table-column prop="address" label="文字描述" width="300">
        </el-table-column>
        <el-table-column prop="zip" label="图片（点击查看大图）">
        </el-table-column>
        <el-table-column label="操作" width="100">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small"
              >查看</el-button
            >
            <el-button type="text" size="small">编辑</el-button>
            <el-button type="text" size="small">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [],
      formInline: {
        user: "",
        region: "",
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
  },
};
</script>

<style>
</style>