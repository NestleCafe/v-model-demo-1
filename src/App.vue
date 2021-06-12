<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>
      文本
      <br />
      <input v-model="message" placeholder="写文本！" />
      <button @click="message = 'frank'">set Message to frank</button>
      <p>Message is: {{ message }}</p>
      <br />
    </div>

    <div>
      多行文本框
      <br />
      <textarea v-model="message2" placeholder="写一段多行文本！"></textarea>
      <span>Multiline message is:</span>
      <p style="white-space: pre-line">{{ message2 }}</p>
      <br />
    </div>

    <div>
      复选框
      <br />
      <label>
        <input type="checkbox" v-model="checked" :value="1" />
        <span>1</span>
      </label>
      <label>
        <input type="checkbox" v-model="checked" :value="2" />
        <span>2</span>
      </label>
      <label>
        <input type="checkbox" v-model="checked" :value="3" />
        <span>3</span>
      </label>
      <label>
        <input type="checkbox" v-model="checked" :value="4" />
        <span>4</span>
      </label>
      <span>Checked names: {{ checked }}</span>
      
    </div>

    <div>
      <br />
      单选框
      <label>
        <input name="radio1" type="radio" v-model="radio" :value="1" />
        <span>1</span>
      </label>
      <label>
        <input name="radio1" type="radio" v-model="radio" :value="2" />
        <span>2</span>
      </label>
      <label>
        <input name="radio1" type="radio" v-model="radio" :value="3" />
        <span>3</span>
      </label>
      <label>
        <input name="radio1" type="radio" v-model="radio" :value="4" />
        <span>4</span>
      </label>
      <span>Checked names: {{ radio }}</span>
      <br />
    </div>

    <div>
      <br />
      下拉列表
      <select v-model="select">
        <option value="">-请选择-</option>
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
      </select>
      <span>Select names: {{ select }}</span>
    </div>
  

  <div>
      <br />
      下拉列表2 数组
      <select v-model="selectText">
        <option value="">-请选择-</option>
        <option v-for="item in arraySelect" :value="item.value" :key="item.value">{{item.text}}</option>

      </select>
      <span>Select names: {{ selectText }}</span>
    </div>

  <div>
    <br />
    登录
    <br />
    <form @submit.prevent="onSubmit">
      <label>
        用户名
        <input type="text" v-model="user.username" />
      </label>

      <label>
        密码
        <input type="password" v-model="user.password" />
      </label>
      <button type="submit">登录</button>

    </form>
  </div>

  </div>

 
</template>


<script>
export default {
  name: "app",
  data() {
    return {
      message: "",
      message2: "",
      checked: [],
      radio: "",
      select:'',
      arraySelect: [
          {text:'选项1', value:1},
          {text:'选项2', value:2},
          {text:'选项3', value:3},
        ],
      selectText: '',
      user:{
          username: '',
          password: '',
      },
    };
  },
  methods:{
    onSubmit(){
      console.log(this.user)
    }
  },
};
</script>
