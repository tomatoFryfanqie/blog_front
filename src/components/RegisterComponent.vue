
<template>
  <div id="RegisterComp">
      <!-- 
        :rules="rules" 传入约定的验证规则
        配合->prop属性使用，设置为需要校验的字段名即可。
        status-icon 为输入框添加了表示校验结果的反馈图标
       -->
      <el-form id="registerFrom" ref="form" label-width="80px"
      :model="form"
      :rules="rules"
      status-icon>

        <el-form-item class="RegisterInput" label="用户名" prop="name">
          <el-input v-model="form.name" ></el-input>
        </el-form-item>

        <el-form-item class="RegisterInput" label="密码" prop="pass">
          <el-input 
          v-model="form.pass"
          type="password"
          ></el-input>
        </el-form-item>

        <el-form-item class="RegisterInput" label="确认密码" prop="checkPass">
          <el-input
          type="password"
          v-model="form.checkPass"
          ></el-input>
        </el-form-item>

        <el-form-item label="性别" class="RegisterInput" prop="sex">
          <el-select v-model="form.sex" placeholder="请选择性别">
            <el-option label="男 / Male" value="male"></el-option>
            <el-option label="女 / Female" value="female"></el-option>
            <el-option label="性别认知障碍 / Two-In-One" value="male?female"></el-option>
          </el-select>
        </el-form-item>

        <el-form-item class="RegisterInput" label="生日" prop="date">
          <el-col :span="11">
            <el-date-picker
              type="date"
              placeholder="选择日期"
              v-model="form.date"
            ></el-date-picker>
          </el-col>
        </el-form-item>

        <el-form-item class="RegisterInput" label="验证方式" prop="checkWay">
          <el-radio-group v-model="form.checkWay">
            <el-radio label="邮箱验证"></el-radio>
            <el-radio label="手机验证"></el-radio>
          </el-radio-group>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" @click="submitForm('form')">注册</el-button>
          <el-button @click="resetForm('form')">重置</el-button>
        </el-form-item>
      </el-form>
  </div>
</template>

<script>
import { ElMessage } from 'element-plus'
  export default {
    name : "RegisterComponent",
    data() {
      var validatePass = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入密码'))
        } else {
          if (this.form.checkPass !== '') {
            this.$refs.form.validateField('checkPass')
          }
          callback()
        }
      }
      var validatePass2 = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请再次输入密码'))
        } else if (value !== this.form.pass) {
          callback(new Error('两次输入密码不一致!'))
        } else {
          callback()
        }
      }
      return {
        form: {
          name: '',
          pass: '',
          checkPass: '',
          sex: '',
          date: '',
          checkWay: ''
        },
        
        rules: {
          name: [
            { required: true, message: '请输入用户名', trigger: 'blur' },
            {
              min: 8,
              max: 25,
              message: '长度在 8 到 25 个字符',
              trigger: 'blur',
            },
          ],
          pass:[
            {required: true, validator: validatePass, trigger: 'blur'},
          ],
          checkPass:[
            {required: true, validator: validatePass2, trigger: 'blur'},
          ],
          sex:[
            {required:true,message:'请选择性别',trigger: 'blur'}
          ],
          date:[
            {type: 'date', required: true, message:'请选择日期', trigger: 'blur'},
          ],
          checkWay:[
            {required: true, message:'请选择验证方式', trigger: 'blur'}
          ]
        }
      }
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            ElMessage.success({
            message: '恭喜你，创建成功',
            type: 'success',
            });
          } else {
            ElMessage.error('错了哦')
            return false
          }
        })
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      },
    },
  }
</script>

<style lang="less" scoped>

#registerFrom{
 margin-top: 50px; 
}
.RegisterInput{
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 22px;
  height: 40px;
  width: 300px;
}

::v-deep .el-icon-circle-check:before {
    color: greenyellow;
}
</style>>