<script setup>
import { ref } from "vue"

const typeOption = ref("")
const stateOption = ref("")
const defectOption = ref("")
const operationTimeOption = ref("")
const options = [
  {
    value: "type",
    label: "Type"
  },
  {
    value: "state",
    label: "State"
  },
  {
    value: "defect",
    label: "Defect"
  },
  {
    value: "operationTime",
    label: "Operation Time"
  }
]

const signboard1 = ref([
  {
    src: "../src/assets/docs/img.png",
    signboard: "凱悅賓館",
    state: "Good",
    defect: "None"
  },
  {
    src: "../src/assets/docs/img_4.png",
    signboard: "駿馬貿易公司",
    state: "Good",
    defect: "None"
  }
])
const signboard2 = ref([
  {
    src: "../src/assets/docs/img_1.png",
    signboard: "英昌風泵零件",
    state: "Bad",
    defect: "Broken"
  },
  {
    src: "../src/assets/docs/img_5.png",
    signboard: "第一公司",
    state: "Good",
    defect: "None"
  }
])
const signboard3 = ref([
  {
    src: "../src/assets/docs/img_2.png",
    signboard: "藝進鋼閘",
    state: "Good",
    defect: "None"
  },
  {
    src: "../src/assets/docs/img_6.png",
    signboard: "榮興貿易",
    state: "Good",
    defect: "None"
  }
])
const signboard4 = ref([
  {
    src: "../src/assets/docs/img_3.png",
    signboard: "牆紙特區",
    state: "Good",
    defect: "None"
  },
  {
    src: "../src/assets/docs/img_7.png",
    signboard: "石雲健鴻",
    state: "Good",
    defect: "None"
  }
])
</script>

<template>
  <div>
    <h2>Query and inspection</h2>
    <div class="query_box">
      <div class="query_item">
        <div>Type:</div>
        <el-select v-model="typeOption" placeholder="Select" style="width: 150px">
          <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
        </el-select>
      </div>

      <div class="query_item">
        <div>State:</div>
        <el-select v-model="stateOption" placeholder="Select" style="width: 150px">
          <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
        </el-select>
      </div>

      <div class="query_item">
        <div>Defect:</div>
        <el-select v-model="defectOption" placeholder="Select" style="width: 150px">
          <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
        </el-select>
      </div>

      <div class="query_item">
        <div>OperationTime:</div>
        <el-select v-model="operationTimeOption" placeholder="Select" style="width: 150px">
          <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
        </el-select>
      </div>
    </div>

    <div style="margin-left: 50px">
      <el-button type="primary">Query</el-button>
      <el-button>Reset</el-button>
    </div>
  </div>

  <div style="display: flex">
    <div class="image-column">
      <div class="image_box" v-for="(signboard, index) in signboard1" :key="index">
        <div class="image-wrapper">
          <img :src="signboard.src" alt="Image 1" class="image-wrapper_image" />
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px">Signboard：</div>
          <div style="font-size: 17px; margin-left: 3px">{{ signboard.signboard }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">State：</div>
          <div :class="signboard.state === 'Good' ? 'good_state' : 'bad_state'">{{ signboard.state }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">Defect：</div>
          <div style="font-size: 17px; margin-left: 3px; margin-top: 5px">{{ signboard.defect }}</div>
        </div>
      </div>
    </div>

    <div class="image-column">
      <div class="image_box" v-for="(signboard, index) in signboard2" :key="index">
        <div class="image-wrapper">
          <img :src="signboard.src" alt="Image 1" class="image-wrapper_image" />
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px">Signboard：</div>
          <div style="font-size: 17px; margin-left: 3px">{{ signboard.signboard }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">State：</div>
          <div :class="signboard.state === 'Good' ? 'good_state' : 'bad_state'">{{ signboard.state }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">Defect：</div>
          <div style="font-size: 17px; margin-left: 3px; margin-top: 5px">{{ signboard.defect }}</div>
        </div>
      </div>
    </div>

    <div class="image-column">
      <div class="image_box" v-for="(signboard, index) in signboard3" :key="index">
        <div class="image-wrapper">
          <img :src="signboard.src" alt="Image 1" class="image-wrapper_image" />
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px">Signboard：</div>
          <div style="font-size: 17px; margin-left: 3px">{{ signboard.signboard }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">State：</div>
          <div :class="signboard.state === 'Good' ? 'good_state' : 'bad_state'">{{ signboard.state }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">Defect：</div>
          <div style="font-size: 17px; margin-left: 3px; margin-top: 5px">{{ signboard.defect }}</div>
        </div>
      </div>
    </div>
    <div class="image-column">
      <div class="image_box" v-for="(signboard, index) in signboard4" :key="index">
        <div class="image-wrapper">
          <img :src="signboard.src" alt="Image 1" class="image-wrapper_image" />
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px">Signboard：</div>
          <div style="font-size: 17px; margin-left: 3px">{{ signboard.signboard }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">State：</div>
          <div :class="signboard.state === 'Good' ? 'good_state' : 'bad_state'">{{ signboard.state }}</div>
        </div>

        <div style="display: flex">
          <div style="font-size: 17px; margin-left: 20px; margin-top: 5px">Defect：</div>
          <div style="font-size: 17px; margin-left: 3px; margin-top: 5px">{{ signboard.defect }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.query_box {
  display: flex;
  justify-content: space-between;
  margin: 20px 0;
}

.image-column {
  display: flex; /* 每行内部使用 flex 布局 */
  flex-wrap: wrap;
  width: 24vw;
  height: 35vh;
  padding: 10px;
}

.image_box {
  width: 100%;
  border: #8d9095 solid 1px;
  border-radius: 10px;
  height: 100%;
  margin-bottom: 20px;
}

.query_item {
  display: flex;
  align-items: center;
}

.image-wrapper {
  display: flex;
  height: 60%;
  width: 100%; /* 让每张图片占据整个列的宽度 */
  margin-top: 2.5%;
  justify-content: center; /* 水平居中 */
  align-items: center; /* 垂直居中 */
}

.image-wrapper_image {
  max-width: 95%; /* 确保图片不超过容器宽度 */
  max-height: 100%; /* 确保图片不超过容器高度 */
  object-fit: contain; /* 确保图片保持其比例并且填充其容器 */
  border-radius: 5px;
  justify-self: center;
}

.good_state {
  font-size: 17px;
  margin-left: 3px;
  margin-top: 5px;
  color: green;
}

.bad_state {
  font-size: 18px;
  margin-left: 3px;
  margin-top: 5px;
  color: red;
  font-weight: bold;
}
</style>
