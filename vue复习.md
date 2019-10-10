## 复习vue
  
  1.vue核心与原生JS开发的区别
   vue核心：数据驱动，组件化（html,css,js） import,export

     .vue(template,js,css)

   原生JS：DOM为主操作

   2.vue常用指令

      v-if:条件渲染  div v-if="false"
      v-show        div v-if="false"
      v-for         div v-for="(item,index) in 数组名" :key="唯一值"
      v-bind        绑定属性    
      v-on          button @click.stop.prevent="方法名"
      v-html        解析html标签  
      v-cloak       由于网络原因，加载慢，可能出现解析问题，例如：出现{{  }}
      v-model       input,select,<textarea v-model=""></textarea>    
      v-text        解析成文本


   3.修饰符（事件，键盘）

     事件修饰符：

     .stop
     .prevent

     键盘：

       butotn @keyup.enter,.up,.down,.left

   4.vue过滤器：主要用于处理数据格式的工具（或者称为数据格式转换的工具）

      {{ message | 过滤器名(1,2) }}

        Vue.filter('过滤器名',function(v1,v2,v3...) {


        })

        filters:function() {


        }
    

   5.自定义指令:封装DOM操作

       Vue.directive('自定义指令名',{
           bind(el,binding,vnode,oldvalue) {},
           inserted(el,binding,vnode,oldvalue) {

           },
           update(el,binding,vnode,oldvalue) {},
           componentUpdated(el,binding,vnode,oldvalue) {},
           unbind() {el,binding,vnode,oldvalue}


       })

      

    ref:获取template中某个dom节点，相当于原生获取dom

     ref用法：

        第一步：给dom节点添加一个ref并命名

        <div ref="box">点击变红色</div>

        第二步：如何获取上面命名的ref

         this.$refs.ref起的名子

          例如：  this.$refs.box

 6.组件传值:

   组件传值三种方式：

    第一种：父->子：主要通过props来传递
       

    第二种：子->父：

       this.$emit('要派发的事件名'，要传递的数据);

       子组件（B组件）写的：传递

      例如： this.$emit('ok',1);

      父组件（A组件）写：接收

        <B @ok="fn"></B>

        methods:{
            fn(v) {
                console.log(v);
            }
        }
        

    第三种：兄弟之间（即非父子）：

       1.通过bus来传递:

       2.vuex


## vuex:

   1.vuex是什么？是一个适用于中大型项目的集中状态管理工具

   2.面试可能会的问题：

    第一个问题：vuex是什么
    第二个问题：什么样的数据放在vuex中：被多个页面之间共享的数据状态，例如：登录，权限，购物车数据等  - +
    第三个问题：vuex的使用流程或原理：

      vue组件---通过dispatch派发到-->actions---通过commit提交到--->mutations--通过操作state--->最终更新组件状态

       actions:异步操作
       mutations:同步操作

    第四个问题：vuex数据持久化问题


=======================

  state:

  actions:

  mutations:

  getters:相当于vue中的计算属性，主要用于复用state中需要通过计算共享的状态

  modules:将state进行模块化管理




