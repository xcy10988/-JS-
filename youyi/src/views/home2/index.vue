<template>
  <div>
    <div class="bai">
      <div class="container">
        <p class="jingping">精品直播</p>
        <div class="div5 clearfix">
          <div style="width: 620px;height: 348px;float: left;">
            <img style="width: 620px;height: 348px;" src="../../assets/1.1首页_r2_c3.png" alt />
          </div>
          <div class="bordershadow">
            <el-tabs v-model="activeName2">
              <el-tab-pane label="今天" name="first">
                <div class="rightdiv">
                  <el-timeline>
                    <el-timeline-item
                      v-for="(activity, index) in activities"
                      :key="index"
                      :icon="activity.icon"
                      :type="activity.type"
                      :color="activity.color"
                      :size="activity.size"
                      :timestamp="activity.timestamp"
                    >{{ activity.content }}</el-timeline-item>
                  </el-timeline>
                </div>
              </el-tab-pane>
              <el-tab-pane label="明天" name="second">
                <div class="rightdiv">
                  <el-timeline>
                    <el-timeline-item
                      v-for="(activity, index) in activities"
                      :key="index"
                      :icon="activity.icon"
                      :type="activity.type"
                      :color="activity.color"
                      :size="activity.size"
                      :timestamp="activity.timestamp"
                    >{{ activity.content }}</el-timeline-item>
                  </el-timeline>
                </div>
              </el-tab-pane>
              <el-tab-pane label="后天" name="third">
                <div class="rightdiv">
                  <el-timeline>
                    <el-timeline-item
                      v-for="(activity, index) in activities"
                      :key="index"
                      :icon="activity.icon"
                      :type="activity.type"
                      :color="activity.color"
                      :size="activity.size"
                      :timestamp="activity.timestamp"
                    >{{ activity.content }}</el-timeline-item>
                  </el-timeline>
                </div>
              </el-tab-pane>
              <el-tab-pane label="10月XX日" name="fourth">
                <div class="rightdiv">
                  <el-timeline>
                    <el-timeline-item
                      v-for="(activity, index) in activities"
                      :key="index"
                      :icon="activity.icon"
                      :type="activity.type"
                      :color="activity.color"
                      :size="activity.size"
                      :timestamp="activity.timestamp"
                    >{{ activity.content }}</el-timeline-item>
                  </el-timeline>
                </div>
              </el-tab-pane>
              <el-tab-pane label="10月XX日" name="fiveth">
                <div class="rightdiv">
                  <el-timeline>
                    <el-timeline-item
                      v-for="(activity, index) in activities"
                      :key="index"
                      :icon="activity.icon"
                      :type="activity.type"
                      :color="activity.color"
                      :size="activity.size"
                      :timestamp="activity.timestamp"
                    >{{ activity.content }}</el-timeline-item>
                  </el-timeline>
                </div>
              </el-tab-pane>
            </el-tabs>
          </div>
        </div>
      </div>
    </div>

    <div class="hui">
      <div class="container">
        <p class="jingping">
          免费好课
          <el-link type="primary" style="float:right">
            更多
            <i class="el-icon-arrow-right"></i>
          </el-link>
        </p>
        <div class="clearfix">
          <div v-for="(item,index) in arr" :key="index" style="cursor:pointer;">
            <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
              <img :src="item.imgsrc" style="width: 248px;height: 150px;" />
              <p class="pname">{{item.classname}}</p>
              <span class="leftspan">{{item.name}}</span>
              <span class="rightspan">杭州XX教育集团</span>
              <span class="bottomspan">免费</span>
            </el-card>
          </div>
        </div>
      </div>
    </div>

    <div class="hui">
      <div class="container">
        <p class="jingping">
          热门课程
          <el-link type="primary" style="float:right">
            更多
            <i class="el-icon-arrow-right"></i>
          </el-link>
        </p>

        <el-tabs v-model="activeName" @tab-click="handleClick">
          <el-tab-pane label="西门子" name="1"></el-tab-pane>
          <el-tab-pane label="东门子" name="2"></el-tab-pane>
          <el-tab-pane label="南门子" name="3"></el-tab-pane>
          <el-tab-pane label="北门子" name="4"></el-tab-pane>
        </el-tabs>

        <div class="clearfix">
          <span v-for="(item,index) in arr2" :key="index" style="cursor:pointer;">
            <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
              <img :src="item.imgsrc" style="width: 248px;height: 150px;" />
              <p class="pname">{{item.classname}}</p>
              <span class="leftspan">{{item.name}}</span>
              <span class="rightspan">杭州XX教育集团</span>

              <span v-if="item.status == 0" class="bottomspan">免费</span>
              <span v-if="item.status == 1" style="color:red" class="bottomspan">
                <span style="font-size:12px;">￥</span>399
                <span class="yuanjia" style="font-size:12px">{{item.yuanjia}}</span>
              </span>
              <span v-if="item.status == 2" style="color:red" class="bottomspan">
                <span style="font-size:12px">￥</span>399
                <span style="font-size:12px;margin-right:10px">底价</span>
                <span class="yuanjia">{{item.yuanjia}}</span>
              </span>
              <span v-if="item.status == 3" style="color:red" class="bottomspan">
                <span style="font-size:12px">￥</span>399
                <span style="font-size:12px;margin-right:10px">拼团价</span>
                <span class="yuanjia">{{item.yuanjia}}</span>
              </span>

              <span class="bottomspanyou" v-if="item.zhekou == 1">
                <span style="font-size:12px">满{{item.man}}减{{item.jian}}</span>
              </span>
              <span class="bottomspanyou" v-if="item.zhekou == 2">
                <span style="font-size:12px">限时{{item.zhe}}折</span>
              </span>
              <span class="bottomspanyou" v-if="item.zhekou == 3">
                <span style="font-size:12px">可用代金券</span>
              </span>
              <span class="bottomspanyou2" v-if="item.zhekou == 4">
                <span style="font-size:12px">砍价中</span>
              </span>
              <span class="bottomspanyou2" v-if="item.zhekou == 5">
                <span style="font-size:12px">拼团中</span>
              </span>
            </el-card>
          </span>
        </div>
      </div>
    </div>

    <div class="bai">
      <div class="container">
        <p class="jingping">
          限时抢购
          <el-link type="primary" style="float:right">
            更多
            <i class="el-icon-arrow-right"></i>
          </el-link>
        </p>

        <div class="clearfix">
          <div v-for="(item,index) in arr3" :key="index" style="cursor:pointer;">
            <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
              <img :src="item.imgsrc" style="width: 248px;height: 150px;" />
              <p class="pname">{{item.classname}}</p>

              <span style="color:red;bottom:60px" class="bottomspan">
                <span style="font-size:12px;">￥</span>399
                <span class="yuanjia" style="font-size:12px">{{item.yuanjia}}</span>
              </span>

              <span class="bottomspanyou2" style="bottom:56px">
                <span style="font-size:12px;">立即秒杀</span>
              </span>

              <p
                style="color:#636d72;position:absolute;bottom:30px;left:10px;font-size:14px"
              >已秒杀{{item.baifenbi}}%</p>
              <p style="position:absolute;bottom:10px;width:100%">
                <el-progress :percentage="item.baifenbi"></el-progress>
              </p>
            </el-card>
          </div>
        </div>
      </div>
    </div>

    <div class="bai">
      <div class="container">
        <p class="jingping">
          优惠套餐
          <el-link type="primary" style="float:right">
            更多
            <i class="el-icon-arrow-right"></i>
          </el-link>
        </p>

        <div class="clearfix">
          <div v-for="(item,index) in arr4" :key="index" style="cursor:pointer;">
            <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
              <img :src="item.imgsrc" style="width: 248px;height: 150px;" />
              <p class="pname">{{item.classname}}</p>
              <span style="color:red;bottom:36px" class="bottomspan">
                <span style="font-size:12px;">￥</span>399
                <span class="yuanjia" style="font-size:12px">{{item.yuanjia}}</span>
              </span>

              <span class="bottomspanyou2" style="bottom:30px">
                <span style="font-size:12px;">
                  {{item.kechengnum}}
                  <br />课程
                </span>
              </span>
            </el-card>
          </div>
        </div>
      </div>
    </div>

    <div class="hui">
      <div class="container">
        <p class="jingping">项目案例</p>
        <div class="clearfix">
          <span v-for="(item,index) in arr5" :key="index" style="cursor:pointer;">
            <el-card class="box-card clearfix" :body-style="{ padding: '0px' }" shadow="hover">
              <img :src="item.imgsrc" style="width: 248px;height: 150px;" />
              <p class="pname">{{item.classname}}</p>
              <span class="leftspan">{{item.name}}</span>
              <span class="rightspan">杭州XX教育集团</span>

              <span v-if="item.status == 0" class="bottomspan">免费</span>
              <span v-if="item.status == 1" style="color:red" class="bottomspan">
                <span style="font-size:12px;">￥</span>399
                <span class="yuanjia" style="font-size:12px">{{item.yuanjia}}</span>
              </span>
              <span v-if="item.status == 2" style="color:red" class="bottomspan">
                <span style="font-size:12px">￥</span>399
                <span style="font-size:12px;margin-right:10px">底价</span>
                <span class="yuanjia">{{item.yuanjia}}</span>
              </span>
              <span v-if="item.status == 3" style="color:red" class="bottomspan">
                <span style="font-size:12px">￥</span>399
                <span style="font-size:12px;margin-right:10px">拼团价</span>
                <span class="yuanjia">{{item.yuanjia}}</span>
              </span>

              <span class="bottomspanyou" v-if="item.zhekou == 1">
                <span style="font-size:12px">满{{item.man}}减{{item.jian}}</span>
              </span>
              <span class="bottomspanyou" v-if="item.zhekou == 2">
                <span style="font-size:12px">限时{{item.zhe}}折</span>
              </span>
              <span class="bottomspanyou" v-if="item.zhekou == 3">
                <span style="font-size:12px">可用代金券</span>
              </span>
              <span class="bottomspanyou2" v-if="item.zhekou == 4">
                <span style="font-size:12px">砍价中</span>
              </span>
              <span class="bottomspanyou2" v-if="item.zhekou == 5">
                <span style="font-size:12px">拼团中</span>
              </span>
            </el-card>
          </span>
        </div>
      </div>
    </div>

    <div class="hui">
      <p class="jingping">全国连锁线下学习校区</p>
      <img src="./../../assets/全国.png" style="width:100%;" draggable="false" />
    </div>

    <div class="hui">
      <div class="container clearfix">
        <p class="jingping">知名机构</p>

        <div
          v-for="(item,index) in arr6"
          :key="index"
          style="float:left;margin-right:20px;width:22.5%;text-align:centeer;"
        >
          <img src="./../../assets/在线.png" style=" border-radius: 50%" />
          <p
            style="font-family: MicrosoftYaHei;font-size: 20px;font-weight: normal;font-stretch: normal;letter-spacing: 0px;color: #252525;"
          >{{item.name}}</p>
          <p
            style="margin-top:10px;text-align:center;font-family: MicrosoftYaHei;font-size: 14px;font-weight: normal;font-stretch: normal;letter-spacing: 0px;color: #252525;"
          >{{item.jieshao}}</p>
        </div>
      </div>
    </div>

    <div class="hui">
      <div class="container clearfix">
        <p class="jingping">优质教师</p>

        <div v-for="(item,index) in arr7" :key="index" class="renwu">
          <img src="./../../assets/头像.png" class="renwuimg" />
          <p class="renwup">{{item.name}}</p>
          <p class="renwup2">{{item.jianjie}}</p>

          <p class="renwup3">
            领域:
            <span style="color:grey">{{item.lingyu}}</span>
          </p>
          <p class="renwup4">
            机构:
            <span style="color:grey">{{item.jigou}}</span>
          </p>
        </div>
      </div>
    </div>

    <div class="hei clearfix">
      <div class="container clearfix" style="text-align:left">
        <el-link class="lianjie">主要链接</el-link>
        <el-link class="lianjie">网站地图</el-link>
        <el-link class="lianjie">联系我们</el-link>
        <el-link class="lianjie">合作院校</el-link>
        <el-link class="lianjie">招贤纳士</el-link>

        <div>
          <div class="zuo">
            <p class="zuop1">联系我们</p>
            <p class="zuop1">免费电话:020-111-1111</p>
            <p class="zuop1">联系地址：广州市白云区京溪街道现象工场3楼308</p>
          </div>

          <div class="you">
            <div class="fd">
              <img src="../../assets/二维码.png" />
              <p>优屹课堂APP</p>
            </div>
            <div class="fd">
              <img src="../../assets/二维码.png" />
              <p>优屹课堂公众号</p>
            </div>
          </div>
        </div>
        <p class="beian">广州优屹课堂教育优先公司 备案号：C 2019 粤ICP备18010410号-1</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      activeName2: 'first',
      jishu: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      jishu2: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱', '西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      jishu3: ['西门子', '三菱', '四菱', '五菱', '六菱', '七菱'],
      pinpai: ['东门子', '3菱', '4菱', '5菱'],
      activities: [
        {
          content: '电工学习指导班级课',
          timestamp: '20:46',
          size: 'large',
          type: 'primary',
          icon: 'el-icon-more'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46',
          color: '#0bbd87'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46',
          size: 'large'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46'
        },
        {
          content: '电工学习指导班级课',
          timestamp: '20:46'
        }
      ],
      arr: [
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费'
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费'
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费'
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费'
        }
      ],
      arr2: [
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 0,
          zhekou: 1,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 1,
          zhekou: 2,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 2,
          zhekou: 3,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 5,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        }
      ],
      activeName: '1',
      arr3: [
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          yuanjia: 987,
          baifenbi: 48
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          yuanjia: 987,
          baifenbi: 48
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          yuanjia: 987,
          baifenbi: 48
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          yuanjia: 987,
          baifenbi: 48
        }
      ],
      arr4: [
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          jiage: 998,
          yuanjia: 99998,
          kechengnum: 6
        }
      ],
      arr5: [
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 0,
          zhekou: 1,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 1,
          zhekou: 2,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 2,
          zhekou: 3,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 5,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        },
        {
          imgsrc: require('@/assets/1.1首页_r2_c2.png'),
          classname: '计算机基础——更适合程序员的编程必备基础知识',
          name: '李老师',
          jigou: 'XX教育集团机构',
          price: '免费',
          status: 3,
          zhekou: 4,
          man: 100,
          jian: 10,
          zhe: 7.5,
          yuanjia: 547
        }
      ],
      arr6: [
        {
          name: '哦是吗哦是吗',
          jieshao: '晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,'
        },
        {
          name: '哦是吗哦是吗哦是吗哦是吗',
          jieshao: '晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,'
        },
        {
          name: '哦是吗哦是吗哦是吗哦是吗',
          jieshao: '晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,'
        },
        {
          name: '哦是吗哦是吗哦是吗哦是吗',
          jieshao: '晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,晓云科技,'
        }
      ],
      arr7: [
        {
          name: 'AAA',
          jianjie: '晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云',
          lingyu: '工业机器人',
          jigou: '远东国际教育集团'
        },
        {
          name: 'AAA',
          jianjie: '晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云',
          lingyu: '工业机器人',
          jigou: '远东国际教育集团'
        },
        {
          name: 'AAA',
          jianjie: '晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云晓云',
          lingyu: '工业机器人',
          jigou: '远东国际教育集团'
        },
        {
          name: 'AAA',
          jianjie: '晓云晓云晓云',
          lingyu: '工业机器人',
          jigou: '远东国际教育集团'
        },
        {
          name: 'AAA',
          jianjie: '晓云晓云晓云',
          lingyu: '工业机器人',
          jigou: '远东国际教育集团'
        }
      ]
    }
  },
  components: {},
  computed: {},
  methods: {
    handleClick (tab, event) {
      console.log(tab, event)
    }
  }
}
</script>

<style scoped>
.bai {
  width: 100%;
  background-color: #ffffff;
  padding: 40px 0;
}

.hui {
  width: 100%;
  background-color: #f8fafc;
  margin: 20px 0;
  padding: 20px 0;
}
.hei {
  width: 100%;
  background-color: #333333;
  margin: 20px 0;
  padding: 20px 0;
}

.jingping {
  text-align: center;
  height: 26px;
  font-family: MicrosoftYaHei-Bold;
  font-size: 24px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 26px;
  letter-spacing: 0px;
  color: #252525;
  margin: 30px 0;
  /* margin-top: 50px; */
}

.bordershadow {
  width: 540px;
  height: 348px;
  float: left;
  padding: 0 18px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12), 0 0 6px rgba(0, 0, 0, 0.04);
}

.rightdiv {
  width: 540px;
  padding-left: 10px;
  height: 290px;
  overflow-y: auto;
}

/* 卡片 */
.pname {
  font-size: 14px;
  text-align: left;
  padding: 10px 15px;
  width: 242px;
  height: 35px;
  font-family: MicrosoftYaHei-Bold;
  font-size: 16px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 17px;
  letter-spacing: 0px;
  color: #252525;
}

.box-card {
  width: 276px;
  height: 300px;
  margin-left: 1.5%;
  margin-top: 20px;
  position: relative;
  float: left;
  padding: 10px 0;
}

.leftspan {
  color: grey;
  font-size: 14px;
  display: inline-block;
  position: absolute;
  bottom: 60px;
  left: 10px;
  height: 14px;
  font-family: MicrosoftYaHei;
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  letter-spacing: 0px;
  color: #999999;
}
.yuanjia {
  font-family: MicrosoftYaHei;
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  letter-spacing: 0px;
  color: #999999;
  text-decoration: line-through;
}
.rightspan {
  color: grey;
  display: inline-block;
  font-size: 14px;
  position: absolute;
  bottom: 60px;
  right: 10px;
  height: 13px;
  font-family: MicrosoftYaHei;
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  letter-spacing: 0px;
  color: #999999;
}

.bottomspan {
  display: inline-block;
  position: absolute;
  bottom: 10px;
  left: 10px;
  font-family: MicrosoftYaHei;
  font-size: 18px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 17px;
  letter-spacing: 0px;
  color: #34d258;
}
.bottomspanyou {
  display: inline-block;
  position: absolute;
  bottom: 10px;
  right: 10px;
  font-family: MicrosoftYaHei;
  font-size: 18px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 17px;
  letter-spacing: 0px;
  color: #0254fe;
  background-color: #ffffff;
  border-radius: 4px;
  border: solid 1px #0254fe;
  padding: 5px 10px;
}
.bottomspanyou2 {
  display: inline-block;
  position: absolute;
  bottom: 10px;
  right: 10px;
  font-family: MicrosoftYaHei;
  font-size: 18px;
  font-weight: normal;
  font-stretch: normal;
  line-height: 17px;
  letter-spacing: 0px;
  padding: 5px 10px;
  color: #fff;
  background-image: linear-gradient(180deg, #1882ff 0%, #0254fe 100%);
  border-radius: 4px;
}
/* 卡片 */

.renwu {
  float: left;
  margin-right: 20px;
  width: 180px;
  text-align: center;
  position: relative;
  height: 220px;
  background-color: #fff;
  margin-top: 50px;
  border-radius: 15px;
  padding: 20px;
  padding-top: 50px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12), 0 0 6px rgba(0, 0, 0, 0.04);
}
.renwuimg {
  border-radius: 50%;
  position: absolute;
  top: -50px;
  left: 60px;
}
.renwup {
  font-family: MicrosoftYaHei;
  font-size: 20px;
  font-weight: normal;
  font-stretch: normal;
  letter-spacing: 0px;
  color: #252525;
  margin-top: 30px;
}
.renwup2 {
  margin-top: 10px;
  text-align: center;
  font-family: MicrosoftYaHei;
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  letter-spacing: 0px;
  color: #999999;
}
.renwup3 {
  text-align: left;
  font-size: 14px;
  margin-top: 10px;
  position: absolute;
  bottom: 60px;
  left: 10px;
}
.renwup4 {
  text-align: left;
  font-size: 14px;
  margin-top: 10px;
  position: absolute;
  bottom: 30px;
  left: 10px;
}
.lianjie {
  color: #fff;
  margin-right: 90px;
}
.hei {
  position: relative;
}
.hei div {
  color: #fff;
  padding-bottom: 15px;
}
.zuo {
  float: left;
  text-align: left;
  margin-top: 40px;
  line-height: 50px;
  letter-spacing: 0px;
  color: #ffffff;
  font-size: 14px;
}
.you {
  float: right;
  text-align: center;
  margin-top: 40px;
  margin-right: 10px;
}
.you .fd:first-child {
  margin-right: 20px;
}
.beian {
  color: #fff;
  text-align: center;
  position: absolute;
  bottom: 10px;
  width: 1200px;
  font-size: 14px;
  border-top: 2px solid #c1c1c1;
  padding-top: 5px;
}
</style>
