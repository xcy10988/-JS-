<template>
  <div>
    <div class="container clearfix">
      <h1 class="h1">优屹课堂</h1>
      <div class="search">
        <el-select
          v-model="value"
          placeholder="请选择"
          style="width: 100px;margin-top: 5px;margin-left:20%;float: left;"
        >
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
          ></el-option>
        </el-select>

        <div style="margin-top: 5px;margin-left:5px;width: 400px;float: left;">
          <el-input placeholder="请输入内容" v-model="input3" class="input-with-select">
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
        </div>
      </div>

      <div class="rightdiv">
        <el-link style="margin-right: 20px;">开课入驻</el-link>
        <el-link style="margin-right: 20px;">消息</el-link>
        <el-link>登陆/注册</el-link>
      </div>
    </div>

    <div class="container">
      <el-tabs v-model="activeName" @tab-click="handleClick">
        <el-tab-pane label="首页" name="1" style="margin-top: 300px;width: 100%;"></el-tab-pane>
        <el-tab-pane label="课程" name="2">课程</el-tab-pane>
        <el-tab-pane label="微课堂" name="3">微课堂</el-tab-pane>
        <el-tab-pane label="活动中心" name="4">活动中心</el-tab-pane>
        <el-tab-pane label="商城" name="5">商城</el-tab-pane>
        <el-tab-pane label="答疑论坛" name="6">答疑论坛</el-tab-pane>
        <el-tab-pane label="下载" name="7">下载</el-tab-pane>
      </el-tabs>
    </div>
    <Shouye v-if="activeName ==1"></Shouye>
    <!-- 轮播图 -->
    <div class="block" v-if="activeName == 1">
      <div style="position: relative;">
        <el-carousel height="330px">
          <el-carousel-item v-for="(item,index) in imgarr" :key="index">
            <!-- <h3 class="small">{{ item }}</h3> -->
            <img :src="item.imgsrc" style="width:100%;height:330px" />
          </el-carousel-item>
        </el-carousel>

        <div class="menu">
          <div>
            <div class="div1">
              <h4 class="h41">
                技术分类
                <i class="el-icon-arrow-right" style="float: right;line-height: 24px;"></i>
              </h4>
              <p class="p1">
                <span class="span1" v-for="(item, index) in jishu" :key="index">{{ item }}</span>
              </p>
              <div class="menu2">
                <p class="pp">
                  <span class="span2" v-for="(item, index) in jishu2" :key="index">{{ item }}</span>
                </p>
                <p class="pp">
                  <span class="span2" v-for="(item, index) in jishu3" :key="index">{{ item }}</span>
                </p>
                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>

                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>

                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>
                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>
              </div>
            </div>

            <div class="div2">
              <h4 class="h41">
                品牌分类
                <i class="el-icon-arrow-right" style="float: right;line-height: 24px;"></i>
              </h4>
              <p class="p2">
                <span class="span1" v-for="(item, index) in pinpai" :key="index">{{ item }}</span>
              </p>
              <div class="menu3">
                <p class="pp">
                  <span class="span2" v-for="(item, index) in jishu2" :key="index">{{ item }}</span>
                </p>
                <p class="pp">
                  <span class="span2" v-for="(item, index) in jishu3" :key="index">{{ item }}</span>
                </p>
                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>

                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>

                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>
                <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
                  <img src="../../assets/1.1首页_r2_c2.png" style="width: 100%" />
                  <p class="pname">JAVA零基础入门JAVA零基础入门JAVA零基础入门</p>
                  <span class="leftspan">￥259</span>
                  <span class="rightspan">杭州XX教育集团</span>
                </el-card>
              </div>
            </div>

            <div class="div3">
              <h4 class="h41">
                优惠课程
                <i class="el-icon-arrow-right" style="float: right;line-height: 24px;"></i>
              </h4>
              <div class="p3"></div>
            </div>

            <div class="div4">
              <h4 class="h41">
                项目案例
                <i class="el-icon-arrow-right" style="float: right;line-height: 24px;"></i>
              </h4>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Shouye from '../home2/index.vue'
export default {
  data () {
    return {
      imgarr: [
        {
          imgsrc: require('@/assets/timg.jpg')
        },
        {
          imgsrc: require('@/assets/timg1.jpg')
        },
        {
          imgsrc: require('@/assets/timg2.jpg')
        }
      ],
      input3: '',
      options: [
        {
          value: '1',
          label: '课程'
        },
        {
          value: '2',
          label: '机构'
        }
      ],
      value: '',
      activeName: '1',
      jishu: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      jishu2: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱', '西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      jishu3: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      pinpai: ['东门子', '3菱', '4菱', '5菱']
    }
  },
  components: {
    Shouye
  },
  computed: {},
  methods: {
    handleClick (tab, event) {
      console.log(tab, event)
    }
  },
  mounted () { }
}
</script>

<style scoped>
.h1 {
  float: left;
  width: 150px;
  height: 50px;
  text-indent: -1000px;
  background: url(../../assets/1.1首页（暂无直播）_r1_c2.png) no-repeat;
  background-size: cover;
}
.search {
  line-height: 50px;
}

.rightdiv {
  float: right;
  line-height: 60px;
}
.menu {
  position: absolute;
  top: 20px;
  left: 18%;
  background-color: #ffffff;
  z-index: 999;
  padding: 0px 0 26px 0;
  border-radius: 15px;
}
.h41 {
  width: 216px;
  text-align: left;
  height: 18px;
  font-family: MicrosoftYaHei;
  font-size: 18px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 24px;
  letter-spacing: 0px;
  color: #252525;
}
.div1 {
  position: relative;
  width: 206px;
  height: 100px;
  background-color: #ffffff;
  padding: 10px;
  padding-bottom: 0;
  border-radius: 15px;
}
.div2 {
  position: relative;
  width: 206px;
  height: 60px;
  background-color: #ffffff;
  padding: 0 10px;
  margin-bottom: 10px;
}
.div3 {
  position: relative;
  width: 206px;
  height: 50px;
  background-color: #ffffff;
  padding: 0 10px;
}
.div4 {
  position: relative;
  width: 206px;
  height: 30px;
  background-color: #ffffff;
  padding: 0 10px;
}
.menu2 {
  display: none;
  position: absolute;
  padding: 15px;
  top: 0px;
  left: 224px;
  width: 984px;
  height: 256px;
  background-color: #f3f9ff;
  border-radius: 0px 8px 8px 0px;border-radius: 15px;
}
.menu3 {
  display: none;
  position: absolute;
  padding: 15px;
  top: -110px;
  left: 224px;
  width: 984px;
  height: 256px;
  background-color: #f3f9ff;
  border-radius: 0px 8px 8px 0px;
}
.div1:hover {
  background-color: #f3f9ff;
}
.div1:hover .menu2 {
  display: block;
}

.div2:hover {
  background-color: #f3f9ff;
}
.div2:hover .menu3 {
  display: block;
}

.span1 {
  margin-right: 10px;
  font-size: 12px;
  color: #82888e;
  display: inline-block;
  margin-bottom: 5px;
}
.span2 {
  margin-right: 50px;
  font-size: 14px;
  color: #000;
  display: inline-block;
  margin-bottom: 10px;
}
.p1 {
  width: 210px;
  text-align: left;
  margin-top: 20px;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  padding-bottom: 10px;
  border-bottom: 1px solid #82888e;
}
.p2 {
  width: 210px;
  text-align: left;
  margin-top: 20px;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  padding-bottom: 5px;
  border-bottom: 1px solid #82888e;
}
.p3 {
  text-align: left;
  border-bottom: 1px solid #82888e;
  margin-top: 30px;
}
.pp {
  text-align: left;
}
.el-select .el-input {
  width: 130px;
}
.input-with-select .el-input-group__prepend {
  background-color: #fff;
}
.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}
.block {
  width: 100%;
  position: absolute;
  top: 102px;
}
.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}

.text {
  font-size: 14px;
}

.item {
  padding: 18px 0;
}

.box-card {
  width: 200px;
  height: 180px;
  margin-left: 4%;
  margin-top: 20px;
  position: relative;
  float: left;
}
.pname {
  font-size: 14px;
  text-align: left;
  padding: 0 10px;
}
.leftspan {
  color: red;
  font-size: 12px;
  display: inline-block;
  position: absolute;
  bottom: 5px;
  left: 5px;
}
.rightspan {
  color: grey;
  display: inline-block;
  font-size: 12px;
  position: absolute;
  bottom: 5px;
}
</style>
