<template>
  <div class="home">
    <h1>from表单封装</h1>
    <!-- 标签显示名称 -->
    <el-form ref="form" :model="form" label-width="100px" :inline="inline">
      <el-form-item v-for="item in formLabel" :key="item.label" :label="item.label">
          <!-- 根据type来显示什么标签 -->
          <el-input :placeholder="'请输入' + item.label" v-if="item.type === 'input'" v-model="form[item.model]"></el-input>
          <el-input :placeholder="'请输入' + item.label" v-else-if="item.type === 'textarea'" v-model="form[item.model]" type="textarea"></el-input>
           <el-select placeholder="请选择" v-if="item.type === 'select'"  v-model="form[item.model]">
            <el-option v-for="item in item.opts" :key="item.value" :label="item.label" :value="item.value" ></el-option>
          </el-select>
          <el-switch v-if="item.type ==='switch'"  v-model="form[item.model]"></el-switch>
          <el-checkbox-group v-if="item.type === 'checkbox'" v-model="form[item.model]">
            <el-checkbox v-for="item in item.checkBox" :key="item.id" :label="item.title" name="type"></el-checkbox>
          </el-checkbox-group>
          <el-radio-group v-model="form[item.model]" v-if="item.type ==='radio'">
            <el-radio v-for="item in item.radioBox"  :key="item.value" :label="item.label" :value='item.value'></el-radio>
          </el-radio-group>
          <el-date-picker
            v-model="form[item.model]"
            v-if="item.type ==='date'"
            type="date"
            value-format='yyyy-MM-dd'
            placeholder="选择日期">
          </el-date-picker>
      </el-form-item>
      <el-form-item><slot></slot></el-form-item>
    </el-form>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  props: {
    formLabel: Array,
    form: Object,
    inline: Boolean
  },
  data () {
    return {
    }
  },
  methods: {
  }
}
</script>
