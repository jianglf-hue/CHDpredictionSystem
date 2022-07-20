<template>

  <el-container>
    <el-header>冠心病预测系统</el-header>
    <el-container>
      <el-aside width="300px">使用说明：

        <el-upload
                class="upload-demo"
                ref="upload"
                action="https://jsonplaceholder.typicode.com/posts/"
                :on-preview="handlePreview"
                :on-remove="handleRemove"
                :file-list="fileList"
                :auto-upload="false">
          <el-button slot="trigger" size="small" type="primary">选取文件</el-button>
          <el-button style="margin-left: 10px;" size="small" type="success" @click="submitUpload">上传到服务器</el-button>
          <div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>
        </el-upload>
      </el-aside>
      <el-main>

        <div>

          <div class="tabLink" >
            <span>性别: </span>
            <el-radio v-model="radio"  label="1">男</el-radio>
            <el-radio v-model="radio" label="2">女</el-radio>
          </div>

          <div class="tabLink">
            <span>吸烟情况：</span>
            <el-radio v-model="radio3"  label="1">有</el-radio>
            <el-radio v-model="radio3" label="2">无</el-radio>
          </div>

          <div class="tabLink">
            <span>中风：</span>
            <el-radio v-model="radio3"  label="1">有</el-radio>
            <el-radio v-model="radio3" label="2">无</el-radio>
          </div>

          <div class="tabLink">
            <span>使用抗高血压药物：</span>
            <el-radio v-model="radio3"  label="1">有</el-radio>
            <el-radio v-model="radio3" label="2">无</el-radio>
          </div>
          <div class="tabLink">
            <span>高血压：</span>
            <el-radio v-model="radio3"  label="1">有</el-radio>
            <el-radio v-model="radio3" label="2">无</el-radio>
          </div>
          <div class="tabLink">
            <span>糖尿病: </span>
            <el-radio v-model="radio3"  label="1">有</el-radio>
            <el-radio v-model="radio3" label="2">无</el-radio>
          </div>

          <div class="tabLink">
            <span>教育水平: </span>
            <el-radio-group v-model="radio2">
              <el-radio v-model="radio2"  label="1">初中及以下</el-radio>
              <el-radio v-model="radio2" label="2">高中</el-radio>
              <el-radio v-model="radio2" label="3">大专</el-radio>
              <el-radio v-model="radio2" label="4">本科</el-radio>
            </el-radio-group>
          </div>

          <div class="tabLink">
            胆固醇含量
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->

          </div>
          <div class="tabLink">
            年龄
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->
          </div>

          <div class="tabLink">
            心率
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->
          </div>

          <div class="tabLink">
            BMI
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->
          </div>

          <div class="tabLink">
            收缩压
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->

          </div>

          <div class="tabLink">
            舒张压
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->

          </div>

          <div class="tabLink">
            吸烟数量
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->

          </div>

          <div class="tabLink">
            血糖
            <el-input
                    placeholder=""
                    style="width: 12%;"
                    v-model="input"
                    clearable>
            </el-input>
            <!--              <el-button>默认按钮</el-button>-->

          </div>
        </div>
        <el-row class="tabLink">


          <el-button type="primary" round>提交内容</el-button>
          <!--            <el-button type="success" round>成功按钮</el-button>-->
          <!--            <el-button type="info" round>信息按钮</el-button>-->
          <!--            <el-button type="warning" round>警告按钮</el-button>-->
          <!--            <el-button type="danger" round>危险按钮</el-button>-->

        </el-row>
      </el-main>
    </el-container>


    <el-footer>版权设计2022</el-footer>
  </el-container>



</template>
<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  .tabLink{
    line-height: 50px;
  }
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 500px;
  }

  body > .el-container {
    margin-bottom: 40px;
  }

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
<script>
  export default {
    data(){
      return {
        // from: "",
        hobby: [],
        gender: "男",
        intro: "",
        radio: '1',
        radio2:"1",
        input:'',
        radio3:''
      }
    }
  }
</script>

<style>

</style>