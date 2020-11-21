<template>
  <div class="plant_list_add">
    <el-tabs v-model="activeName" type="card">
      <el-tab-pane label="信息" name="first">
        <el-form
          :model="ruleForm"
          :rules="rules"
          ref="ruleForm"
          label-width="100px"
          class="demo-ruleForm"
        >
          <el-form-item label="编号" prop="name">
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="中文名（植物名）" prop="region">
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="拉丁学名" required>
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="别名" required>
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="药材名" required>
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="文字描述" required>
            <el-input
              type="textarea"
              placeholder="请输入内容"
              v-model="ruleForm.textarea"
            ></el-input>
          </el-form-item>
          <el-form-item label="花期和果期" required>
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="地理分布" required>
            <el-select v-model="ruleForm.region" placeholder="区域">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="生境" required>
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="药用部位" prop="type">
            <el-checkbox-group v-model="ruleForm.type">
              <el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
              <el-checkbox label="地推活动" name="type"></el-checkbox>
              <el-checkbox label="线下主题活动" name="type"></el-checkbox>
              <el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
            </el-checkbox-group>
          </el-form-item>
          <el-form-item label="适应症/用法" required>
            <el-input
              type="textarea"
              placeholder="请输入内容"
              v-model="ruleForm.textarea"
            ></el-input>
          </el-form-item>
          <el-form-item label="性质" required>
            <el-checkbox-group v-model="ruleForm.type">
              <el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
              <el-checkbox label="地推活动" name="type"></el-checkbox>
              <el-checkbox label="线下主题活动" name="type"></el-checkbox>
              <el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
            </el-checkbox-group>
          </el-form-item>
          <el-form-item label="其他" prop="resource">
            <el-input
              type="textarea"
              placeholder="请输入内容"
              v-model="ruleForm.textarea"
            ></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="submitForm('ruleForm')"
              >下一步</el-button
            >
          </el-form-item>
        </el-form>
      </el-tab-pane>
      <el-tab-pane label="图片" name="second">
        <el-row :gutter="20">
          <el-col :span="6">
            <el-card class="box-card" header="生境">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="全株">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="根">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="茎">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
        </el-row>
        <el-row :gutter="20">
          <el-col :span="6">
            <el-card class="box-card" header="叶">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="花">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="果实">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
          <el-col :span="6">
            <el-card class="box-card" header="种子">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
            </el-card>
          </el-col>
        </el-row>
        <el-row :gutter="20">
          <el-col :span="6">
            <el-card class="box-card" header="手绘图">
              <el-upload
                class="upload-demo"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="(file, fileList) => handleRemove(file, fileList)"
                :file-list="fileList"
                list-type="picture"
                :limit="1"
              >
                <el-button size="small" type="primary">点击上传</el-button>
                <div slot="tip" class="el-upload__tip">
                  只能上传jpg/png文件，且不超过500kb
                </div>
              </el-upload>
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
      fileList: [
        {
          name: "food.jpeg",
          url:
            "https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100",
        },
      ],
      ruleForm: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: "",
      },
      rules: {
        name: [
          { required: true, message: "请输入活动名称", trigger: "blur" },
          { min: 3, max: 5, message: "长度在 3 到 5 个字符", trigger: "blur" },
        ],
        region: [
          { required: true, message: "请选择活动区域", trigger: "change" },
        ],
        date1: [
          {
            type: "date",
            required: true,
            message: "请选择日期",
            trigger: "change",
          },
        ],
        date2: [
          {
            type: "date",
            required: true,
            message: "请选择时间",
            trigger: "change",
          },
        ],
        type: [
          {
            type: "array",
            required: true,
            message: "请至少选择一个活动性质",
            trigger: "change",
          },
        ],
        resource: [
          { required: true, message: "请选择活动资源", trigger: "change" },
        ],
        desc: [{ required: true, message: "请填写活动形式", trigger: "blur" }],
      },
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    },
    handleRemove(file, fileList) {
      console.log(file, fileList);
    },
    handlePreview(file) {
      console.log(file);
    },
  },
};
</script>

<style lang="scss">
.el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
</style>