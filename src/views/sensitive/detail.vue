<template>
  <div class="app-container sensitive-page">
    <div class="filter-container" />
    <el-table
      :data="tableData"
      fit
    >
      <el-table-column prop="group_name" label="分组" width="150" align="center" />
      <el-table-column prop="version" label="版本" width="90" align="center" />
      <el-table-column prop="product" label="产品" width="90" align="center" />
      <el-table-column prop="rule" label="规则" width="150" align="center">
        <template slot-scope="{row}">
          <span v-if="row.rule" class="link-type" @click="handleFetchRule(row.rule)">{{ row.rule }}</span>
        </template>
      </el-table-column>
      <el-table-column prop="file_path" label="文件路径" width="300" align="left" />
      <el-table-column prop="line_no" label="行号" width="120" align="center" />
      <el-table-column label="Status" class-name="status-col" width="100">
        <template slot-scope="{row}">
          <el-tag :type="row.sheilded | sheildedFilter">
            {{ row.sheilded ? '已屏蔽' : '未屏蔽' }}
          </el-tag>
        </template>
      </el-table-column>

      <el-table-column label="Actions" align="center" width="230" class-name="small-padding fixed-width">
        <template slot-scope="{row}">
          <el-button type="primary" size="mini" @click="handleDetail(row)">
            详细
          </el-button>
          <el-button v-if="!row.sheilded" size="mini" type="warning" @click="handleSheild(row,'published')">
            屏蔽
          </el-button>
          <el-button v-if="row.sheilded" size="mini" @click="handleSheild(row,'draft')">
            取消屏蔽
          </el-button>
        </template>
      </el-table-column>
    </el-table>
    <el-dialog :visible.sync="dialogRuleVisible" title="规则详情">
      <el-table :data="ruleData" border fit highlight-current-row style="width: 100%" :show-header="false">
        <el-table-column prop="field" label="字段" />
        <el-table-column prop="value" label="值" />
      </el-table>
      <span slot="footer" class="dialog-footer">
        <el-button type="primary" @click="dialogRuleVisible = false">Confirm</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: 'SensitiveDetail',
  filters: {
    sheildedFilter(sheilded) {
      return sheilded ? 'warning' : 'info'
    }
  },
  props: {},
  data() {
    return {
      dialogRuleVisible: false,
      ruleData: null,
      tableData: [
        {
          group_name: 'Group1',
          version: '23A',
          product: '4G',
          rule: 'todo',
          file_path: 'src/views/sensitive/index.vue',
          line_no: 33,
          line_text: '# TODO: Build API',
          sheilded: true
        },
        {
          group_name: 'Group2',
          version: '23A',
          product: '4G',
          rule: 'fixme',
          file_path: 'src/views/sensitive/index.vue',
          line_text: '# FIXME: poor performance',
          line_no: 134,
          sheilded: false
        },
        {
          group_name: 'Group2',
          version: '23A',
          product: '4G',
          rule: 'fixme',
          file_path: 'src/views/sensitive/detail.vue',
          line_text: '# FIXME: Dead loop',
          line_no: 114,
          sheilded: false
        }
      ],
      rules: {
        todo: { id: '1', name: 'todo', desc: 'todo in code', type: '敏感信息', regex: '\\bto\\s*do\\b', exclude: ['\\w+ to do \\w+'] },
        fixme: { id: '2', name: 'fixme', desc: 'fixme in code', type: '敏感信息', regex: '\\bfix\\s*me\\b', exclude: [] }
      }

    }
  },
  created() {},
  mounted() {},
  methods: {
    handleFetchRule(rule_name) {
      // fetchRule(rule).then(response => {
      //   this.ruleData = response.data.ruleData
      //   this.dialogRuleVisible = true
      // })
      this.ruleData = this.tableFormatRuleData(this.rules[rule_name])
      this.dialogRuleVisible = true
    },
    tableFormatRuleData(ruleData) {
      return Object.keys(ruleData).map(attr => {
        return { 'field': attr, 'value': ruleData[attr] }
      })
    }
  }

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
