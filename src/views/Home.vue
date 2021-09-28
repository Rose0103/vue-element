<template>
  <div class="home">
    <common-form :formLabel="formLabel" :form="form" :inline="false">
      <el-button type="primary" @click="submit()">提交</el-button>
    </common-form>
    <common-table :tableData="tableData"></common-table>
  </div>
</template>

<script>
import CommonForm from '../components/CommonForm.vue'
import CommonTable from '../components/CommonTable.vue'
export default {
  name: 'Home',
  components: {
    CommonForm,
    CommonTable
  },
  data () {
    return {
      formLabel: [
        {
          model: 'name',
          label: '姓名',
          type: 'input'
        },
        {
          model: 'createDate',
          label: '创建日期',
          type: 'date'
        },
        {
          model: 'department',
          label: '部门',
          type: 'select',
          opts: [
            {
              label: '技术部',
              value: 1
            },
            {
              label: '财务部',
              value: 2
            }
          ]
        },
        {
          model: 'enable',
          label: '是否启用',
          type: 'switch'
        },
        {
          model: 'hobby',
          label: '兴趣爱好',
          type: 'checkbox',
          checkBox: [
            {
              id: 1,
              title: '唱歌'
            },
            {
              id: 2,
              title: '逛街'
            },
            {
              id: 3,
              title: '看书'
            }

          ]
        },
        {
          model: 'sex',
          label: '性别',
          type: 'radio',
          radioBox: [
            { label: '男', value: 1 },
            { label: '女', value: 0 }
          ]
        },
        {
          model: 'remarks',
          label: '备注',
          type: 'textarea'
        }
      ],
      form: {
        name: '',
        department: '',
        enable: false,
        hobby: [],
        sex: '',
        remarks: '',
        createDate: ''
      },
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  },
  methods: {
    submit () {
      console.log(this.form)
    }
  }
}
</script>
