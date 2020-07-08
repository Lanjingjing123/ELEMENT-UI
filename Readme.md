# 1. VUE 实战-ELMENT-UI 

## 1.1 项目搭建

- 安装node.js,使用命令：node -v 
- 全局安装vue 脚手架,命令：cnpm install -g  @vue/cli 
- 查看vue脚手架安装成功：vue -V

## 1.2 vue中组件中传值常用的几种方式

- 父子组件传值

  - props/$emit

  - $parent/children

  - $ref

    ```
    1. 父组件给子组件传值
    	1.1 父组件Parent.vue中增加v-bind:msg msg为绑定的key
    		 <m-child v-bind:msgParent="'from Parent msg'></m-child> 
    	1.2 子组件 Child.vue 增加 props
    		  props: {
                msgParent: {
                    type: String,
                    default: ''
                },
           	  },
        1.3 获取值
        <h5>{{msgParent}}</h5>
    2. 子组件给父组件传值
    	2.1 子组件(Child.vue) 增加事件
    	<button @click="passMsg">走你!</button>
    	2.2 子组件(Child.vue)增加方法 将子组件的事件发送给父组件
    	   methods: {
                passMsg() {
                    this.$emit('showMsg',"I am from Child")
                }
            },
        2.3 父组件（Parent.vue）进行 监听showMsg 事件（@showMsg），然后进行值获取
         <m-child v-bind:msgParent="'from Parent msg'" @showMsg="showMsg"></m-child>
        </div>
        
        
          data() {
                return {
                    msg: ''
                }
            },
         	methods: {
                showMsg(val) {
                    this.msg = val
                }
            },
        2.4 获取值
        <h3>{{msg}}</h3>
    
    ```

    

