<template>
  <div class="app-container sensitive-page">
    <div>
      <el-button
        style="margin: 0 0 20px 20px"
        type="primary"
      >屏蔽管理</el-button>
      <el-button
        style="margin: 0 0 20px 20px"
        type="primary"
      >配置管理</el-button>
      <el-button
        style="margin: 0 0 20px 20px"
        type="primary"
      >规则管理</el-button>
    </div>

    <el-table :data="tableData" :row-class-name="tableRowClassName" fit>
      <el-table-column
        prop="group_name"
        label="分组"
        width="150"
        align="center"
      />
      <el-table-column label="敏感信息" align="center">

        <el-table-column v-for="rule in rules" :key="rule" :prop="rule" :label="rule" width="120" align="center">
          <template slot-scope="{row}">
            <template v-if="row[rule] > 0">
              <router-link :to="{name: 'SensitiveDetail'}">
                <el-link type="primary">{{ row[rule] }}</el-link>
              </router-link>
            </template>
            <template v-else>
              <el-link type="text" disabled>{{ row[rule] }}</el-link>
            </template>
          </template>
        </el-table-column>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'Sensitive',
  props: {},
  data() {
    return {
      tableData: [
        {
          group_name: 'Group1',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10
        },
        {
          group_name: 'Group2',
          rule1: 0,
          rule2: 0,
          rule3: 0,
          rule4: 0
        },
        {
          group_name: 'Group3',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10
        },
        {
          group_name: 'Group4',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10
        }
      ]
    }
  },
  computed: {
    rules: function() {
      const rules = []

      if (this.tableData.length !== 0) {
        Object.keys(this.tableData[0]).forEach(item => {
          if (item !== 'group_name') {
            rules.push(item)
          }
        })
      }
      return rules
    }
  },
  created() {},
  mounted() {
  },
  methods: {
    tableRowClassName({ row, rowIndex }) {
      for (let i = 0; i < this.rules.length; i++) {
      // for (rule of this.rules) {
        if (row[this.rules[i]] > 0) {
          return 'warning-row'
        }
      }
      return ''
    }
  }
}
</script>

<style lang="scss">
.sensitive-page {
  .warning-row {
    background: oldlace;
  }
}
</style>
