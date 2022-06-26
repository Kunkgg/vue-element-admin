<template>
  <div class="app-container sensitive-page">

    <div class="filter-container">
      <el-select v-model="listQuery.version" style="width: 90px" class="filter-item" @change="handleFilter">
        <el-option v-for="item in versionOptions" :key="item" :label="item" :value="item" />
      </el-select>
      <el-select v-model="listQuery.product" style="width: 90px" class="filter-item" @change="handleFilter">
        <el-option v-for="item in productOptions" :key="item" :label="item" :value="item" />
      </el-select>
      <el-button class="filter-item" type="primary" icon="el-icon-setting">屏蔽管理</el-button>
      <el-button class="filter-item" type="primary" icon="el-icon-setting">规则管理</el-button>
      <el-button class="filter-item" type="primary" icon="el-icon-setting">配置管理</el-button>
      <el-button v-waves :loading="downloadLoading" class="filter-item" type="primary" icon="el-icon-download" @click="handleDownload">
        Export
      </el-button>
    </div>

    <el-table :data="list" :row-class-name="tableRowClassName" fit>
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
import waves from '@/directive/waves' // waves directive
import { parseTime } from '@/utils'

export default {
  name: 'Sensitive',
  directives: { waves },
  props: {},
  data() {
    return {
      list: null,
      listQuery: {
        page: 1,
        limit: 20,
        version: '23A',
        product: '4G'
      },
      listLoading: true,
      downloadLoading: false,
      tableData: [
        {
          group_name: 'Group1',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10,
          version: '23A',
          product: '4G'
        },
        {
          group_name: 'Group2',
          rule1: 0,
          rule2: 0,
          rule3: 0,
          rule4: 0,
          version: '23A',
          product: '4G'
        },
        {
          group_name: 'Group3',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10,
          version: '23A',
          product: '4G'
        },
        {
          group_name: 'Group4',
          rule1: 10,
          rule2: 0,
          rule3: 20,
          rule4: 10,
          version: '23A',
          product: '4G'
        }
      ],
      versionOptions: ['23B', '23A', '22B', '22A'],
      productOptions: ['4G', '5G']
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
  created() {
    this.getList()
  },
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
    },
    getList() {
      this.listLoading = true

      // call api
      console.log(this.listQuery)
      this.list = this.tableData
      setTimeout(() => {
        this.listLoading = false
      }, 1.5 * 1000)
    },
    handleFilter() {
      this.listQuery.page = 1
      this.getList()
    },
    handleDownload() {
      this.downloadLoading = true
      import('@/vendor/Export2Excel').then(excel => {
        const tHeader = ['group_name', 'rule1', 'rule2', 'rule3', 'rule4', 'version', 'product']
        const filterVal = ['group_name', 'rule1', 'rule2', 'rule3', 'rule4', 'version', 'product']
        const data = this.formatJson(filterVal)
        console.log(data)
        excel.export_json_to_excel({
          header: tHeader,
          data,
          filename: `whitebox-security-${this.listQuery.version}-${this.listQuery.product}`
        })
        this.downloadLoading = false
      })
    },
    formatJson(filterVal) {
      return this.list.map(v => filterVal.map(j => {
        if (j === 'timestamp') {
          return parseTime(v[j])
        } else {
          return v[j]
        }
      }))
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
