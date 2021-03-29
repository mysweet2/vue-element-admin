<template>
  <div class="app-container user-container">
    <el-form
      :inline="true"
      :model="formInline"
      class="demo-form-inline"
      align="center"
    >
      <el-form-item label="用户姓名">
        <el-input v-model="formInline.user" placeholder="模糊查询"></el-input>
      </el-form-item>
      <el-form-item label="用户状态">
        <el-select v-model="formInline.region" placeholder="是否有效">
          <el-option label="有效" value="EBL"></el-option>
          <el-option label="无效" value="DBL"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">查询</el-button>
      </el-form-item>
    </el-form>
    <el-table
      :data="tableData"
      border
      fit
      highlight-current-row
      style="width: 100%"
    >
      <el-table-column align="center" prop="date" label="创建日期" width="180">
      </el-table-column>
      <el-table-column align="center" prop="name" label="姓名" width="180">
      </el-table-column>
      <el-table-column
        align="center"
        prop="telephone"
        label="手机号"
        width="180"
      >
      </el-table-column>
      <el-table-column align="center" prop="address" label="地址">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formInline: {
        user: '',
        region: ''
      },
      tableData: []
    }
  },
  methods: {
    onSubmit() {
      this.tableData = [{ name: '余鹏飞', telephone: '13671885828' }]
    }
  }
}
</script>

