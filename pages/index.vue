<template>
  <div id="top-view-wrapper">
    <el-tabs stretch>
      <el-tab-pane label="ダチのめし募集">
        めしりすと
      </el-tab-pane>
      <el-tab-pane label="自分のめし募集">
        じぶんのめしりすと
      </el-tab-pane>
      <el-tab-pane label="ダチリスト">
        だちのりすと
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import makeAuthHeaderBody from '../plugins/id-token'

export default {
  layout : 'AuthPage',
  methods:{
    async sendPrivate(){
      const authHeader = await makeAuthHeaderBody();
      const res = await this.$axios.get('http://localhost:3000/private' ,{
        headers: authHeader
      })
      console.log(res)
    }
  }
}
</script>

<style>
#top-view-wrapper {
  max-width : 800px;
  margin-top: 15px;
  margin-left: auto;
  margin-right: auto;
}
.el-tab-pane{
  padding: 10px 15px 10px 15px;
}
</style>

