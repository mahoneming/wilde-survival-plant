<template>
  <div class="identify_basis_list">
    <el-row :gutter="20">
      <el-col v-for="item in cardList" :key="item.name" :span="6">
        <el-card class="box-card" :header="item.name" @click.native="linkToDetail(item.name)">
          <el-image
            style="width: 100px; height: 100px"
            :src="item.url"
            fit="fill"
          ></el-image>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeName: "first",
      cardList: [
        {
          name: "根",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
        {
          name: "茎",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
        {
          name: "叶",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
        {
          name: "花",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
        {
          name: "果实",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
        {
          name: "种子",
          url:
            "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
        },
      ],
      srcList: [
        "https://fuss10.elemecdn.com/8/27/f01c15bb73e1ef3793e64e6b7bbccjpeg.jpeg",
      ],
    };
  },
  methods: {
    linkToDetail(type) {
      console.log(type)
      this.$router.push({
        path: '/plantlib/identifybasis/detail',
        query: type
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