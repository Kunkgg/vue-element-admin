<template>
  <div class="app-container sensitive-page">
    <div class="filter-container" />
    <el-table
      :data="tableData"
      fit
    >
      <el-table-column
        prop="group_name"
        label="分组"
        width="150"
        align="center"
      />
      <el-table-column
        prop="rule"
        label="规则"
        width="120"
        align="center"
      />
      <el-table-column
        prop="file_path"
        label="文件路径"
        width="300"
        align="left"
      />
      <el-table-column
        prop="line_no"
        label="行号"
        width="120"
        align="center"
      />
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'SensitiveDetail',
  props: {},
  data() {
    return {
      tableData: [
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        },
        {
          group_name: 'Group1',
          rule: 'rule1',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33
        },
        {
          group_name: 'Group1',
          rule: 'rule351',
          file_path: 'src/views/table/dynamic-table/components/FixedThead.vue',
          line_no: 4601
        }
      ]
    }
  },
  created() {},
  mounted() {},
  methods: {}
}
</script>

<style>
.el-table .warning-row {
  background: oldlace;
}
.el-table .warning-row {
  background: oldlace;
}
</style>
