# VUE

vue的核心库只关注视图层，方便与[第三方库](https://so.csdn.net/so/search?q=第三方库&spm=1001.2101.3001.7020)或既有项目整合。

HTML + CSS + JS : 视图 ： `给用户看，刷新后台给的数据`

网络通信：axios

页面跳转：vue-router

状态管理：vuex

Vue-UI : ICE , Element UI



## 一、前端核心分析

### 1. Vue概述

**Vue**是一款渐进式JavaScript框架，所谓渐进式就是逐步实现新特性的意思，如实现模块化开发、路由、状态管理等新特性。其特点是综合了Angular (模块化)和React (虚拟DOM)的优点



### 2. 前端三要素

- HTML (结构) :超文本标记语言(Hyper Text Markup Language) ，决定网页的结构和内容
- CSS (表现) :层叠样式表(Cascading Style sheets) ，设定网页的表现样式
- JavaScript (行为) :是一种弱类型脚本语言，其源代码不需经过编译，而是由浏览器解释运行,用于控制网页的行为



### 3. JavaScrip框架

- **jQuery**: 大家熟知的JavaScript框架，优点是简化了DOM操作，缺点是DOM操作太频繁,影响前端性能;在前端眼里使用它仅仅是为了兼容IE6、7、8;
- **Angular**: Google收购的前端框架，由一群Java程序员开发，其特点是将后台的MVC模式搬到了前端并增加了模块化开发的理念，与微软合作，采用TypeScript语法开发;对后台程序员友好，对前端程序员不太友好;最大的缺点是版本迭代不合理(如: 1代-> 2代，除了名字，基本就是两个东西;截止发表博客时已推出了Angular6)
- **React**: Facebook出品，一款高性能的JS前端框架;特点是提出了新概念[虚拟DOM]用于减少真实DOM操作，在内存中模拟DOM操作，有效的提升了前端渲染效率;缺点是使用复杂，因为需要额外学习一门[JSX] 语言;
- **Vue**:一款渐进式JavaScript框架，所谓渐进式就是逐步实现新特性的意思，如实现模块化开发、路由、状态管理等新特性。其特点是综合了Angular (模块化)和React (虚拟DOM)的优点;
- **Axios** :前端通信框架;因为Vue 的边界很明确，就是为了处理DOM,所以并不具备通信能力，此时就需要额外使用一个通信框架与服务器交互;当然也可以直接选择使用jQuery提供的AJAX通信功能;



**前端三大框架：Angular、React、Vue**

```
Angular的模块化开发
View：JSP{{}}
DATA:
vm：数据双向绑定

React的虚拟DOM：利用内存

**计算属性：Vue的特色**
```





## 二、第一个Vue程序

```
在IDEA中安装Vue.js插件
```



导入vue

new一个vue对象

绑定一个元素

放入数据

从模板里取出来

### 1. 什么是MVVM

```
MVVM (Model-View-ViewModel) 是一种软件架构设计模式，由微软WPF (用于替代WinForm，以前就是用这个技术开发桌面应用程序的)和Silverlight (类似于Java Applet,简单点说就是在浏览器上运行的WPF)的架构师Ken Cooper和Ted Peters 开发，是一种简化用户界面的事件驱动编程方式。由John Gossman (同样也是WPF和Silverlight的架构师)于2005年在他的博客上发表。
```

MVVM 源自于经典的MVC (ModI-View-Controller) 模式。MVVM的核心是ViewModel层，负责转换Model中的数据对象来让数据变得更容易管理和使用，其作用如下:

- **该层向上与视图层进行双向数据绑定**
- **向下与Model层通过接口请求进行数据交互**

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-dZfj6UVP-1595254922257)(D:\我\MyBlog\狂神说 VUE 笔记.assets\image-20200717215124290.png)]](https://img-blog.csdnimg.cn/20200720222239842.png)



### 2. 为什么要使用MVVM

MVVM模式和MVC模式一样，主要目的是分离视图(View)和模型(Model),有几大好处：

1. **低耦合**:视图(View)可以独立于Model变化和修改,一个ViewModel可以绑定到不同的
   View上，当View变化的时候Model可以不变，当Model变化的时候View也可以不变。
2. **可复用:**你可以把一些视图逻辑放在一个ViewModel里面，让很多View重用这段视图逻辑。
3. **独立开发**:开发人员可以专注于业务逻辑和数据的开发(ViewModel),设计人员可以专注于页面设计。
4. **可测试**:界面素来是比较难于测试的，而现在测试可以针对ViewModel来写。



### 3. Vue是MVVM模式的实现者

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-n9t7FtSN-1595254922262)(D:\我\MyBlog\狂神说 VUE 笔记.assets\image-20200717181433248.png)]](https://img-blog.csdnimg.cn/20200720222311692.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0RERERlbmdf,size_16,color_FFFFFF,t_70)

- Model：模型层，在这里表示JavaScript
- View：视图层,在这里表示DOM (HTML操作的元素)
- ViewModel：连接视图和数据的中间件，Vue.js就是MVVM中的ViewModel层的实现者在MVVM架构中，是不允许数据和视图直接通信的，只能通过ViewModel来通信，而ViewModel就是定义了一个Observer观察者
- ViewModel能够观察到数据的变化，并对视图对应的内容进行更新
- ViewModel 能够监听到视图的变化，并能够通知数据发生改变



**Vue在线cdn：**

```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
```



#### **简单的例子**

1. 代码

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>Title</title>
   
   </head>
   <body>
   
   <!--view层，模板-->
   <div id="app">
       {{message}}
   </div>
   
   
   <!--导入vue.js-->
   <script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
   
   <!--控制视图层-->
   <script>
       var vm = new Vue({
           /*元素绑定*/
           el: "#app",
           // Model:数据
           data:{
               message: "hello vue!"
           }
       });
   </script>
   </body>
   </html>
   ```

2. 效果图

   ![image-20221028133842859](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028133842859.png)

3. 在控制台上修改后的效果图

   ![image-20221028134220216](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028134220216.png)





## 三、Vue的基本语法

### 0. 七大对象

==Vue的七大对象：[vue七大对象 - 简书 (jianshu.com)](https://www.jianshu.com/p/296f9484d016)==



### 1. v-bind

现在数据和DOM已经被建立了关联，所有的东西都是响应式的。我们在控制台操作对象的属性，界面可以实时更新。我们可以使用`v-bind`来绑定元素属性！

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

</head>
<body>

<!--view层，模板-->
<div id="app">
    <span v-bind:title="message">
        鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>
    var vm = new Vue({
        /*元素绑定*/
        el: "#app",
        // Model:数据
        data:{
            message: "hello vue!"
        }
    });
</script>
</body>
</html>
```

![image-20221028141610084](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028141610084.png)

**提示信息为hello vue**



在Console上进行修改

![image-20221028142119998](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028142119998.png)



**提示信息为wangmudao**





### 2. v-if/v-else

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>

</head>
<body>

<!--view层，模板-->
<div id="app">
  <h1 v-if="ok">YES</h1>
  <h1 v-else>NO</h1>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>
  var vm = new Vue({
    /*元素绑定*/
    el: "#app",
    // Model:数据
    data:{
      ok: true
    }
  });
</script>
</body>
</html>
```



![image-20221028143253926](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028143253926.png)

在Console上进行修改

![image-20221028143336076](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028143336076.png)







### 3. v-if/v-else-if/v-else

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>

</head>
<body>

<!--view层，模板-->
<div id="app">
  <h1 v-if="type==='A'">A</h1>
  <h1 v-else-if="type==='B'">B</h1>
  <h1 v-else>C</h1>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>
  var vm = new Vue({
    /*元素绑定*/
    el: "#app",
    // Model:数据
    data:{
      type: 'A'
    }
  });
</script>
</body>
</html>
```



结果：由A变为B再变为C，最后还是C

![image-20221028143911514](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028143911514.png)





### 4. v-for

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<!--view层，模板-->
<div id="app">
  <li v-for="item in items">
    {{item.name}}
  </li>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>
  var vm = new Vue({
    /*元素绑定*/
    el: "#app",
    // Model:数据
    data:{
        // 数组，存放一个个对象
      items: [
        {name: "王慕道"},
        {name: "Mudao.Wang"}
      ]
    }
  });
</script>
</body>
</html>
```

![image-20221028151323525](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028151323525.png)

### 5. v-on

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app">
  <button v-on:click="saiHi">
    点击我
  </button>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>
  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",
    // 数据
    data: {
      message: "王慕道"
    },
    // 方法，必须定义在Vue的methods中
    methods: {
      // 方法名: 方法体(){}
      saiHi: function () {
        alert(this.message)
      }
    }


  });
</script>
</body>
</html>
```

![image-20221028151521924](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028151521924.png)





## 四、Vue的双向绑定（v-model）



### 1. 什么是双向绑定

Vue.js是一个MVVM框架，即数据双向绑定,即当数据发生变化的时候,视图也就发生变化，当视图发生变化的时候，数据也会跟着同步变化。这也算是Vue.js的精髓之处了。

 值得注意的是，我们所说的数据双向绑定，一定是对于UI控件来说的，非UI控件不会涉及到数据双向绑定。单向数据绑定是使用状态管理工具的前提。如果我们使用vuex，那么数据流也是单项的，这时就会和双向数据绑定有冲突。


### 2. 为什么要实现数据的双向绑定

在Vue.js 中，如果使用vuex ，实际上数据还是单向的，之所以说是数据双向绑定，这是用的UI控件来说，对于我们**处理表单**，Vue.js的双向数据绑定用起来就特别舒服了。即两者并不互斥，**在全局性数据流使用单项,方便跟踪;局部性数据流使用双向，简单易操作。**



### 3. 在表单中使用双向数据绑定

你可以用==v-model==`指令在表单 <input>、<textarea> 及<select>元素上创建双向数据绑定。它会根据控件类型自动选取正确的方法来更新元素。尽管有些神奇，但`v-model`本质上不过是语法糖。它负责监听户的输入事件以更新数据，并对一些极端场景进行一些特殊处理。

==**v-model会忽略所有元素的value、checked、selected特性的初始值而总是将Vue实例的数据作为数据来源，你应该通过JavaScript在组件的data选项中声明。**==





- input场景

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Title</title>
  </head>
  <body>
  <div id="app">
    输入的文本：<input type="text" v-model="message"> {{message}}
  </div>
  
  <!--导入vue.js-->
  <script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
  
  <!--控制视图层-->
  <script>
    var vm = new Vue({
      // 绑定视图部分的元素
      el: "#app",
      // 数据
      data: {
        message: "123"
       }
    });
  </script>
  </body>
  </html>
  ```

  **结果：**

  初始值为vue对象中data的定义的message的值123

  ![image-20221028160047230](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028160047230.png)

  在文本中输入其他数字和字符会同时改变

  ![image-20221028160159407](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028160159407.png)







- textarea场景

  ![image-20221028160614747](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028160614747.png)

  改变后同input一样





- select场景（下拉框）

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Title</title>
  </head>
  <body>
  <div id="app" >
    <select v-model="selected">
      <option value="" disabled>--请选择--</option>
      <option >A</option>
      <option >B</option>
      <option >C</option>
    </select>
    <h2>你选择的是{{selected}}</h2>
  </div>
  
  <!--导入vue.js-->
  <script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
  
  <!--控制视图层-->
  <script>
    var vm = new Vue({
      // 绑定视图部分的元素
      el: "#app",
      // 数据
      data: {
        selected: ""
       }
    });
  </script>
  </body>
  </html>
  ```

  结果：

  ![image-20221028161451673](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028161451673.png)

  ![image-20221028161524069](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221028161524069.png)

  





## 五、Vue组件

组件是可复用的`Vue`实例，说白了就是一组可以重复使用的模板，跟JSTL的自定义标签、Thymeleaf的`th:fragment` 等框架有着异曲同工之妙。通常一个应用会以一棵嵌套的组件树的形式来组织：

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-oSJ7c1GT-1595254922264)(D:\我\MyBlog\狂神说 VUE 笔记.assets\image-20200718095216872.png)]](https://img-blog.csdnimg.cn/20200720222347392.png)

### 1. 注册组件

```html
<!--组件对象的名称可任意取，组件对象中存在两个参数 
1、props：用于接收Vue对象的值  2、template：用于定义要输出的值的模板-->

Vue,component("组件名称",{组件对象})
```



### 2. 简单使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app" >
  <!--组件的使用-->
  <mudao></mudao>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>

  // 定义一个Vue的组件component(也可认为组件即自定义标签)
  Vue.component("mudao",{
      template: '<li>Hello</li>'+
              '<li>Vue</li>'
  });

  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",

  });
</script>
</body>
</html>
```



### 3. 跟Vue对象结合使用



**基本流程：**

在Vue对象==vm==中存在一个==数组==，现在需要将这个数组在自定义的==组件mudao==中遍历输出

基本流程：先将数组==items==在==组件（标签）==中通过==v-for==遍历出每一个==item==，然后通过v-bind将每一个==item==绑定到自定义的参数==wang==上，之后再通过组件中的==props==参数接收==wang==，再通过组件中的==template==将数据输出



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app" >
  <mudao v-for="item in items" v-bind:wang="item"></mudao>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>

  // 定义一个Vue的组件component(也可认为组件即自定义标签)
  Vue.component("mudao",{
      // props用于接收参数
      props: ['wang'],
      template: '<li>{{wang}}</li>'
  });

  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",
    // 数据
    data: {
      items: ['Java','Linux','前端']
    }

  });
</script>
</body>
</html>
```





## 六、Axios通信



### 1. 什么是Axios

Axios是一个开源的可以用在浏览器端和`NodeJS` 的异步通信框架，她的主要作用就是实现AJAX异步通信，其功能特点如下:

- 从浏览器中创建XMLHttpRequests
- 从node.js创建http请求
- 支持Promise API [JS中链式编程]
- 拦截请求和响应

- 转换请求数据和响应数据

- 取消请求

- 自动转换JSON数据

### 2. Vue的生命周期

[(14条消息) Vue生命周期详解_渣渣苏的博客-CSDN博客_vue的生命周期](https://blog.csdn.net/su2231595742/article/details/115186957)



### 3. 为什么使用Axios

由于Vue.js是一个视图层框架且作者(尤雨溪) 严格准守SoC (关注度分离原则)，所以Vue.js并不包含Ajax的通信功能，为了解决通信问题，作者单独开发了一个名为vue-resource的插件，不过在进入2.0 版本以后停止了对该插件的维护并推荐了Axios 框架。少用jQuery，因为它操作Dom太频繁 !



==模拟Json数据：==

```json
{
  "name": "Mudao",
  "age": "22",
  "sex": "男",
  "url":"https://www.baidu.com",
  "address": {
    "street": "通惠中路",
    "city": "杭州",
    "country": "中国"
  },
  "links": [
    {
      "name": "bilibili",
      "url": "https://www.bilibili.com"
    },
    {
      "name": "baidu",
      "url": "https://www.baidu.com"
    },
    {
      "name": "cqh video",
      "url": "https://www.4399.com"
    }
  ]
}
```



==初次使用==

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="vue">

</div>


<!--1.导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
<!--导入axios-->
<script src="https://cdn.bootcdn.net/ajax/libs/axios/0.19.2/axios.min.js"></script>
<script>

  var vm = new Vue({
    el: "#vue",
      // 钩子函数,基本上在mounted函数上写AJAX请求,
      mounted(){  // 链式编程
          // 先拿到json数据，然后通过响应在控制台打印出数据
          axios.get('../data.json').then(resp=>(console.log(resp.data)));
      }
  })
</script>

</body>
</html>
```



==控制台打印的数据==

![image-20221031111033165](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031111033165.png)



==json文件的格式==

![image-20221031111240492](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031111240492.png)











==进阶使用==

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="vue">
    <div>{{info.name}}</div>
    <div>{{info.age}}</div>
    <div>{{info.sex}}</div>
    <div>{{info.address}}</div>
    <!--href中不可直接填info.url，必须先进行绑定-->
    <a v-bind:href="info.url">点我</a>
</div>


<!--1.导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>
<!--导入axios-->
<script src="https://cdn.bootcdn.net/ajax/libs/axios/0.19.2/axios.min.js"></script>
<script>

  var vm = new Vue({
    el: "#vue",

    // data是Vue对象的属性
    data: {
        items: ['java','vue']
    },

    // data()是Vue对象的方法,用于接收数据
    data(){
        // 方法的返回
        return{
            // info可自动绑定resp中的各个属性
            info:{
                // 返回的参数，必须和获取的json字符串一样
                name: null,
                age: null,
                sex: null,
                url: null,
                address: {
                    street: null,
                    city: null,
                    country: null
                }
            }
        }
    },

    // 钩子函数,基本上在mounted函数上写AJAX请求，现在用于写axios
    mounted(){  // 链式编程
        // 先拿到json数据，然后通过响应获取数据给Vue对象中的data()方法的参数赋值
        axios.get('../data.json').then(resp=>(this.info=resp.data));
    }
  });
</script>

</body>
</html>
```



==效果展示==

![image-20221031114159605](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031114159605.png)

- 点击“点我”跳转到"https://www.baidu.com"





### 4. vue的计算属性

 计算属性的重点突出在`属性`两个字上(属性是名词)，首先它是个`属性`其次这个属性有`计算`的能力(计算是动词)，这里的计算就是个函数;简单点说，它就是一个能够将计算结果缓存起来的属性(将行为转化成了静态的属性)，仅此而已;可以想象为**缓存**！

==以时间为例子==

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app" >
    <p>currentTime1 {{currentTime1()}}</p>
    <p>currentTime2 {{currentTime2}}</p>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>


    var vm = new Vue({
        // 绑定视图部分的元素
        el: "#app",
        // 数据
        data: {
            message: "hello,vue"
        },
        // 方法
        methods: {
            // currentTime1方法用于返回当前时间
            currentTime1: function () {
                // 返回一个时间戳
                return Date.now();
            }
        },

        // 计算属性
        computed: {
            // currentTime2方法用于返回当前时间
            currentTime2: function () {
                // 返回一个时间戳
                return Date.now();
            }
        }
    });
</script>
</body>
</html>
```





==效果图==

![image-20221031120939580](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031120939580.png)





==使用**方法（methods）**和**计算属性（computed）**的区别:==

- 在methods中调用方法需要加上小括号，currentTime1()

- 而在computed中调用属性只需要名字，currentTime2

- 使用computed相当于将数据进行缓存，只有通过改变方法中的值从而使缓存失效从而重新进行缓存，而methods没有缓存功能

  在currentTime2中添加this.message用于观测数据的变化

  ![image-20221031122100643](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031122100643.png)

  

  **结论：**调用方法时，每次都需要进行计算，既然有计算过程则必定产生系统开销，那如果这个结果是不经常变化的呢?此时就可以考虑将这个结果缓存起来，采用计算属性可以很方便的做到这一点,**计算属性的主要特性就是为了将不经常变化的计算结果进行缓存，以节约我们的系统开销;**

  



### 5. 内容分发（插槽/slot）

==步骤：==

1. 定义父组件，然后在模板中定义两个插槽，并定义相应的插槽名字
2. 定义两个子组件，确认数据传输的参数以及模板
3. 新建Vue对象，绑定元素以及定义数据
4. 将父组件写在body中然后将子组件写在父组件中，并将子组件的插槽属性与父组件的插槽名字绑定
5. 最后将子组件中的参数与Vue对象中的数据进行绑定

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app" >
    <!--父组件-->
    <todo>
        <!--子组件-->
        <!--slot="子组件数据要插入的插槽的名字"-->
        <todo-title slot="title" v-bind:title="title"></todo-title>
        <!--子组件-->
        <todo-items slot="items" v-for="item in items" v-bind:item="item"></todo-items>
    </todo>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>

    // slot标签用于定义插槽
    Vue.component("todo",{
        template:
            '<div>' +
                '<slot name="title"></slot>' +
                '<ul>' +
                '<slot name="items"></slot>' +
                '</ul>' +
            '</div>'
    });

    Vue.component("todo-title",{
        props: ['title'],
        template:
            '<div>{{title}}</div>'
    });

    Vue.component("todo-items",{
        props: ['item'],
        template:
            '<li>{{item}}</li>'
    });




  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",
    // 数据
    data: {
        title: "插槽",
        items: ['Java','Vue']
    }

  });
</script>
</body>
</html>
```



==效果图==

![image-20221031151031942](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031151031942.png)



### 6. 自定义事件内容分发



==在组件中定义方法并且在模板中调用(部分代码，其余代码跟内容分发相同)==

```html
Vue.component("todo-items",{
        props: ['item'],
        template:
            '<li>{{item}} <button v-on:click="remove">删除</button></li>',
        methods: {
        	<!--定义方法，点击按钮就出现“删除”提示-->
            remove: function () {
                alert("删除")
            }
        }
    });
```

==效果图==

![image-20221031152913727](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031152913727.png)







==在Vue对象中定义删除方法并且在控制台测试(部分代码，其余代码跟内容分发相同)==

```html
  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",
    // 数据
    data: {
        title: "插槽",
        items: ['Java','Vue']
    },
    methods: {
        removeItem: function (index) {
            // 打印需要删除的数组元素
            console.log("删除了"+this.items[index]);
            // 删除vm中item数组中指定的元素，splice(删除元素的下表，删除的个数，添加的元素...)
            this.items.splice(index,1);
        }
    }

  });
```



![image-20221031153846153](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031153846153.png)





==在组件中删除Vue实例中的数据==

- 在未使用自定义事件前，组件只能调用该组件中定义的方法，不能调用Vue实例中的方法，
- 使用自定义事件
  - 先在视图部分使用**v-on:自定义事件名(removediy)="vue实例中的事件名(removeItem(参数))"**
  - 在组件的方法中使用**this.$emit (‘自定义事件名’,参数)**，==注意：该参数要和vue实例中的事件的参数一致==

![image-20221031162607427](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031162607427.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app" >
    <!--父组件-->
    <todo>
        <!--子组件-->
        <!--slot="子组件数据要插入的插槽的名字"-->
        <todo-title slot="title" v-bind:title="title"></todo-title>

        <!--子组件-->
        <todo-items slot="items" v-for="(item,index) in items"
                    v-bind:item="item" v-bind:index="index" v-on:removediy="removeItem(index)"></todo-items>
    </todo>
</div>

<!--导入vue.js-->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5.21/dist/vue.min.js"></script>

<!--控制视图层-->
<script>

    // slot标签用于定义插槽
    Vue.component("todo",{
        template:
            '<div>' +
                '<slot name="title"></slot>' +
                '<ul>' +
                '<slot name="items"></slot>' +
                '</ul>' +
            '</div>'

    });

    Vue.component("todo-title",{
        props: ['title'],
        template:
            '<div>{{title}}</div>',
    });

    Vue.component("todo-items",{
        props: ['item','index'],
        template:
            '<li>{{item}}.{{index}} <button v-on:click="remove">删除</button></li>',
        methods: {
            remove: function (index) {
                this.$emit("removediy",index)
            }
        }
    });




  var vm = new Vue({
    // 绑定视图部分的元素
    el: "#app",
    // 数据
    data: {
        title: "插槽",
        items: ['Java','Vue']
    },
    methods: {
        removeItem: function (index) {
            // 打印需要删除的数组元素
            console.log("删除了"+this.items[index]);
            // 删除vm中item数组中指定的元素，splice(删除元素的下表，删除的个数，添加的元素...)
            this.items.splice(index,1);
        }
    }

  });
</script>
</body>
</html>
```



==效果图==

![image-20221031165455510](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031165455510.png)

点击删除，触发事件，成功删除

![image-20221031165551433](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221031165551433.png)





## 入门小结

核心：数据驱动，组件化

优点∶借鉴了AngulaJS的模块化开发和React的虚拟Dom，虚拟Dom就是把Dom操作放到内存中执行

常用的属性：

- v-if, v-else-if, v-else
- v-for
- v-on 绑定事件，简写 @
- v-model 数据双向绑定
- v-bind 给组件绑定参数，简写 :

组件化:

- 组合组件slot插槽
- 组件内部绑定事件需要使用到this.$emit("事件名",参数)
- 计算属性的特色,缓存计算数据

遵循SoC关注度分离原则，Vue是纯粹的视图框架，并不包含比如Ajax之类的通信功能，为了解决通信问题，我们需要使用Axios 框架做异步通信







## 七、vue-cli



### 1. 什么是vue-cli

vue-cli 官方提供的一个脚手架，用于快速生成一个 vue 的项目模板，预先定义好的目录结构及基础代码，就好比咱们在创建 Maven 项目时可以选择创建一个骨架项目，这个骨架项目就是脚手架，我们的开发更加的快速。

**主要功能：**

- 统一的目录结构
- 本地调试
- 热部署
- 单元测试
- 集成打包上线





### 2.需要的环境

- Node.js ：[http://nodejs.cn/download/](https://link.zhihu.com/?target=http%3A//nodejs.cn/download/)
- Git : [https://git-scm.com/downloads](https://link.zhihu.com/?target=https%3A//git-scm.com/downloads) 镜像:[https://npm.taobao.org/mirrors/git-for-windows/](https://link.zhihu.com/?target=https%3A//npm.taobao.org/mirrors/git-for-windows/) （暂未用到）



npm是 JavaScript 软件包管理工具,并且是 Node.js （会自动安装npm）平台的默认包管理工具。通过npm可以安装、共享、分发代码,管理项目依赖关系。

在命令行分别可通过 node -v 和 npm -v 查看版本号

安装 Node.js 淘宝镜像加速器（cnpm）下载会快很多（尽量少用）

```
# -g 就是全局安装
npm install cnpm -g

# 若安装失败，则将源npm源换成淘宝镜像
# 因为npm安装插件是从国外服务器下载，受网络影响大
npm config set registry https://registry.npm.taobao.org

# 然后再执行
npm install cnpm -g
```



### 3. 安装vue-cli

```
#在命令台输入
cnpm install vue-cli -g
#查看是否安装成功
vue list
```



### 4. 第一个 vue-cli 应用程序

在C:\学习代码\vue创建一个基于 webpack 模板的 vue 应用程序

```
# 这里的 myvue 是项目名称，可以根据自己的需求起名
vue init webpack myvue

```

一路都选择no即可;

 初始化并运行

```
cd myvue
npm install
npm run dev
```

执行完成后,目录多了很多依赖

![image-20221101091804972](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101091804972.png)





## 八、 webpack

### 1. 什么是webpack

本质上，webpack是一个现代JavaScript应用程序的静态模块打包器(module bundler)。当webpack处理应用程序时，它会递归地构建一个依赖关系图(dependency graph),其中包含应用程序需要的每个模块，然后将所有这些模块打包成一个或多个bundle.
 Webpack是当下最热门的前端资源模块化管理和打包工具，它可以将许多松散耦合的模块按照依赖和规则打包成符合生产环境部署的前端资源。还可以将按需加载的模块进行代码分离，等到实际需要时再异步加载。通过loader转换，任何形式的资源都可以当做模块，比如CommonsJS、AMD、ES6、 CSS、JSON、CoffeeScript、LESS等;
 伴随着移动互联网的大潮，当今越来越多的网站已经从网页模式进化到了WebApp模式。它们运行在现代浏览器里，使用HTML5、CSS3、ES6 等新的技术来开发丰富的功能，网页已经不仅仅是完成浏览器的基本需求; WebApp通常是一个SPA (单页面应用) ，每一个视图通过异步的方式加载，这导致页面初始化和使用过程中会加载越来越多的JS代码，这给前端的开发流程和资源组织带来了巨大挑战。
 前端开发和其他开发工作的主要区别，首先是前端基于多语言、多层次的编码和组织工作，其次前端产品的交付是基于浏览器的，这些资源是通过增量加载的方式运行到浏览器端，如何在开发环境组织好这些碎片化的代码和资源，并且保证他们在浏览器端快速、优雅的加载和更新，就需要一个模块化系统，这个理想中的模块化系统是前端工程师多年来一直探索的难题。、



### 2.下载webpack

webpack 是一款**模块加载器兼打包工具**，它能把各种资源，如 JS、JSX、ES6、SASS、LESS、图片等**都作为模块来处理和使用。**

==安装==

```
npm install webpack -g
npm install webpack-cli -g
```

==测试安装成功: 输入以下命令有版本号输出即为安装成功==

```
webpack -v
webpack-cli -v
```

![image-20221101103441326](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101103441326.png)



### 3. 使用webpack

1. 在vue目录下创建空文件夹webpack-study，使用IDE打开

2. 在项目中创建modules文件夹用于存放js文件

3. 在modules中创建模块文件hello.js

   ```javascript
   // 暴露一个方法
   exports.sayHi = function () {
       document.write("<h1>Mudao</h1>>")
   }
   ```

4. 在modules中创建入口文件main.js

   ```javascript
   // require用于获取同级目录下的hello.js文件
   var hello = require("./hello")
   hello.sayHi()
   ```

5. 在项目目录下创建配置文件webpack.config.js

   ```javascript
   module.exports = {
       /**entry作为入口
        *output作为输出出口
        *  filename是文件生成的路径以及名称（规范）
        *
        * */
       entry: './modules/main.js',
       output: {
           filename: './js/bundle.js'
       }
   
   }
   ```

6. 在终端使用webpack命令进行打包，在项目目录下生成dist/js/bundles.js

   ```javascript
   (()=>{var r={645:(r,t)=>{t.sayHi=function(){document.write("<h1>Mudao</h1>>")}}},t={};(function o(e){var i=t[e];if(void 0!==i)return i.exports;var n=t[e]={exports:{}};return r[e](n,n.exports,o),n.exports})(645).sayHi()})();
   ```

7. 在项目目录下创建主页面index.html，引入打包好的bundles.js

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>Title</title>
   </head>
   <body>
   <script src="dist/js/bundle.js"></script>
   </body>
   </html>
   ```

8. 打开页面

   ![image-20221101111800667](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101111800667.png)

==可以使用webpack --watch（监听）实现热部署==

![image-20221101112547593](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101112547593.png)



注意点（参考）：

出现Module not found: Error: Can't resolve './src'信息：

1. webpack.config.js不在根目录
2. 名字必须叫webpack.config.js
3. 目录正确
4. main.js在新版本里不可以，应该改成index.js什么的，反正不可以用main











## 九、vue-router路由

 Vue Router是Vue.js官方的路由管理器（路径跳转）。它和Vue.js的核心深度集成，让构建单页面应用变得易如反掌。包含的功能有:

嵌套的路由/视图表

模块化的、基于组件的路由配置

路由参数、查询、通配符

基于Vue.js过渡系统的视图过渡效果

细粒度的导航控制

带有自动激活的CSS class的链接

HTML5历史模式或hash模式，在IE9中自动降级

自定义的滚动条行为


### 1. 安装

基于第一个vue-cli进行测试学习;先查看node_modules中是否存在 vue-router
 vue-router 是一个插件包，所以我们还是需要用 npm/cnpm 来进行安装的。打开命令行工具，进入你的项目目录，输入下面命令。

```
npm install vue-router --save-dev

这里报错的先用cnpm install vue-router@3.1.3 --save-dev命令再运行，因为可能是router版本太高了
```



### 2. vue-router demo实例

1. 将之前案例由vue-cli生成的案例用idea打开

2. 清理不用的东西 assert下的logo图片 component定义的helloworld组件 我们用自己定义的组件

3. 清理代码 以下为清理之后的代码 src下的App.vue 和main.js以及根目录的index.html
   ==这三个文件的关系是 index.html 调用main.js 调用App.vue==

   
   

**index.html**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <title>myvue</title>
  </head>
    
  <body>
    <div id="app">
    </div>

  </body>
</html>
```



**main.js**

```js
import Vue from 'vue'
import App from './App'

Vue.config.productionTip = false

new Vue({
  el: '#app',
  components: { App },
  template: '<App/>'
})
```



**App.vue**

```vue
<template>
  <div id="app">
    <h1>1</h1>

  </div>
</template>

<script>
export default {
  name: 'App',

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```



4. 在components目录下创建自己的组件Content.vue、Main.vue和Wang.vue

   Content.vue

   ```vue
   <template>
     <h1>这是一个内容页</h1>
   </template>
   
   <script>
   /*用于导出组件*/
   export default {
     name: "Content"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

   Main.vue

   ```vue
   <template>
     <h1>这是一个首页</h1>
   </template>
   
   <script>
   export default {
     name: "Main"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

   Wang.vue

   ```vue
   <template>
     <h1>王</h1>
   </template>
   
   <script>
   export default {
     name: "Wang"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

5. 在src目录下创建router文件夹并在其中创建配置文件index.js（官方要求）

   index.js（路由的主配置）

   ```js
   import Vue from "vue";
   //导入路由插件
   import VueRouter from "vue-router";
   
   //导入需要使用的组件
   import Content from "../components/Content";
   import Main from "../components/Main";
   import Wang from "../components/Wang";
   
   // 显示声明使用导入的VueRouter
   Vue.use(VueRouter);
   
   // 配置导出路由
   export default new VueRouter({
     routes: [
       {
         // 路由路径
         path: '/content',
         // 路由名称
         name: 'Content',
         // 跳转的组件
         component: Content
       },
       {
         // 路由路径
         path: '/main',
         // 路由名称
         name: 'main',
         // 跳转的组件
         component: Main
       },
       {
         path: '/wang',
         name: 'wang',
         component: Wang
       }
     ]
   });
   ```

6. 将配置导入主配置文件中

   ```js
   import Vue from 'vue'
   import App from './App'
   // 导入路由的配置文件(只要配置文件叫做index就不用在路径中说明)
   import router from './router'
   
   Vue.config.productionTip = false
   
   
   new Vue({
     el: '#app',
     components: { App },
     /*将导入的路由写入vue对象中*/
     router,
     template: '<App/>'
   })
   ```

7. 在主Vue文件（App.vue）中使用

   ```vue
   <template>
     <div id="app">
       <h1>Mudao</h1>
       <router-link to="/content">内容</router-link>
       <router-link to="/main">首页</router-link>
       <router-link to="/wang">Mudao</router-link>
       
       <!--用于显示组件中的内容-->
       <router-view></router-view>
     </div>
   </template>
   ..
   ```

8. 开启运行环境（npm run dev）,在浏览器测试

   ![image-20221101143834482](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101143834482.png)

   -----------------------------------------------------------------------------------------------------------------------------------------------------

   ![image-20221101143911719](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101143911719.png)

   ![image-20221101144037269](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101144037269.png)

   









## 十、Vue+ElementUI

根据之前创建vue-cli项目一样再来创建一个新项目

1. 创建一个名为 hello-vue 的工程

   ```
   vue init webpack hello-vue
   ```

   

2. 安装依赖，我们需要安装 `vue-router`、`element-ui`、`sass-loader` 和`node-sass` 四个插件

   ```
   # 进入工程目录
   cd hello-vue
   # 安装 vue-router
   npm install vue-router --save-dev
   # 安装 element-ui
   npm i element-ui -S
   # 安装依赖
   npm install
   # 安装 SASS 加载器
   cnpm install sass-loader node-sass --save-dev
   # 启动测试
   npm run dev	
   ```

   

3. **Npm命令解释**

   ```
   npm install moduleName：安装模块到项目目录下
   npm install -g moduleName：-g 的意思是将模块安装到全局，具体安装到磁盘的哪个位置，要看 npm config prefix的位置
   npm install moduleName -save：–save的意思是将模块安装到项目目录下，并在package文件的dependencies节点写入依赖，-S为该命令的缩写
   npm install moduleName -save-dev：–save-dev的意思是将模块安装到项目目录下，并在package文件的devDependencies节点写入依赖，-D为该命令的缩写
   ```

   

4. 创建成功后用idea打开，并删除净东西 创建views和router文件夹用来存放视图和路由

   ![image-20221101153648918](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101153648918.png)

5. 在views创建Main.vue

   **Main.vue**

   ```vue
   <template>
     <h1>首页</h1>
   </template>
   
   <script>
   export default {
     name: "Main"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

   

6. 在views中创建Login.vue视图组件

   **Login.vue:**（用的ElementUI中的代码）

   ```vue
   <template>
     <div>
       <el-form ref="loginForm" :model="form" :rules="rules" label-width="80px" class="login-box">
         <h3 class="login-title">欢迎登录</h3>
         <el-form-item label="账号" prop="username">
           <el-input type="text" placeholder="请输入账号" v-model="form.username"/>
         </el-form-item>
         <el-form-item label="密码" prop="password">
           <el-input type="password" placeholder="请输入密码" v-model="form.password"/>
         </el-form-item>
         <el-form-item>
           <el-button type="primary" v-on:click="onSubmit('loginForm')">登录</el-button>
         </el-form-item>
       </el-form>
   
       <el-dialog
         title="温馨提示"
         :visible.sync="dialogVisible"
         width="30%"
         :before-close="handleClose">
         <span>请输入账号和密码</span>
         <span slot="footer" class="dialog-footer">
           <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
         </span>
       </el-dialog>
     </div>
   </template>
   
   <script>
   export default {
     name: "Login",
     data() {
       return {
         form: {
           username: '',
           password: ''
         },
   
         // 表单验证，需要在 el-form-item 元素中增加 prop 属性
         rules: {
           username: [
             {required: true, message: '账号不可为空', trigger: 'blur'}
           ],
           password: [
             {required: true, message: '密码不可为空', trigger: 'blur'}
           ]
         },
   
         // 对话框显示和隐藏
         dialogVisible: false
       }
     },
     methods: {
       onSubmit(formName) {
         // 为表单绑定验证功能
         this.$refs[formName].validate((valid) => {
           if (valid) {
             // 使用 vue-router 路由到指定页面，该方式称之为编程式导航
             this.$router.push("/main");
           } else {
             this.dialogVisible = true;
             return false;
           }
         });
       }
     }
   }
   </script>
   
   <style lang="scss" scoped>
   .login-box {
     border: 1px solid #DCDFE6;
     width: 350px;
     margin: 180px auto;
     padding: 35px 35px 15px 35px;
     border-radius: 5px;
     -webkit-border-radius: 5px;
     -moz-border-radius: 5px;
     box-shadow: 0 0 25px #909399;
   }
   
   .login-title {
     text-align: center;
     margin: 0 auto 40px auto;
     color: #303133;
   }
   </style>
   ```

7. 创建路由

   在 router 目录下创建一个名为 index.js 的 vue-router 路由配置文件

   **index.js**

   ```js
   import Vue from "vue";
   import router from "vue-router";
   import Main from "../views/Main";
   import Login from "../views/Login";
   
   Vue.use(router);
   
   export default new router({
     routes: [
       {
         path: '/main',
         name: 'Main',
         component: Main
       },
       {
         path: '/login',
         name: 'Login',
         component: Login
       }
     ]
   })
   ```

8. 在main.js中配置相关

   main.js是index.html调用的 所以前面注册的组件要在这里导入

   **一定不要忘记扫描路由配置并将其用到new Vue中**

   **main.js**

   ```js
   import Vue from 'vue'
   import App from './App'
   // 扫描路由配置
   import router from './router'
   // 导入elementUI
   import ElementUI from "element-ui"
   // 导入element css
   import 'element-ui/lib/theme-chalk/index.css'
   
   Vue.use(ElementUI);
   
   /* eslint-disable no-new */
   new Vue({
     el: '#app',
     router,
     // ElementUI规定这样使用
     render: h => h(App)
   
   })
   ```

9. 在App.vue中配置显示视图

   ```vue
   <template>
     <div id="app">
       <router-link to="/main">首页</router-link>
       <router-link to="/login">login</router-link>
       <router-view></router-view>
   
     </div>
   </template>
   
   <script>
   
   
   export default {
     name: 'App',
     components: {
   
     }
   }
   </script>
   
   <style>
   #app {
     font-family: 'Avenir', Helvetica, Arial, sans-serif;
     -webkit-font-smoothing: antialiased;
     -moz-osx-font-smoothing: grayscale;
     text-align: center;
     color: #2c3e50;
     margin-top: 60px;
   }
   </style>
   ```

10. 测试

    ```
    npm run dev
    ```

    ![image-20221101161234002](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101161234002.png)

    ![image-20221101161256617](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221101161256617.png)

    ==注意：如果不成功的话可以删除Login.vue中样式的lang="scss"==

    **原因：项目没有对scss进行支持，需要另外安装第三方包的依赖来对scss进行解析**





## 十一、路由嵌套

嵌套路由又称子路由，在实际应用中，通常由多层嵌套的组件组合而成。

==只有在父路由下配置子路由，才能在父组件中发起有关子组件的调用（相当于局部更新数据）==





1. 创建用户信息组件，在 views/user 目录下创建一个名为 Profile.vue 的视图组件；

   **Profile.vue**

   ```vue
   <template>
     <h1>个人信息</h1>
   </template>
   
   <script>
   export default {
     name: "Profile"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

2. 在用户列表组件在 views/user 目录下创建一个名为 List.vue 的视图组件；

   **List.vue**

   ```vue
   <template>
     <h1>用户列表</h1>
   </template>
   
   <script>
   export default {
     name: "List"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

3. 修改首页视图，我们修改 Main.vue 视图组件，此处使用了 ElementUI 布局容器组件，代码如下：

   **Main.vue**

   ```vue
   <template>
     <div>
       <el-container>
         <el-aside width="200px">
           <el-menu :default-openeds="['1']">
             <el-submenu index="1">
               <template slot="title"><i class="el-icon-caret-right"></i>用户管理</template>
               <el-menu-item-group>
                 <el-menu-item index="1-1">
                   <!--插入的地方-->
                   <router-link to="/user/profile">个人信息</router-link>
                 </el-menu-item>
                 <el-menu-item index="1-2">
                   <!--插入的地方-->
                   <router-link to="/user/list">用户列表</router-link>
                 </el-menu-item>
               </el-menu-item-group>
             </el-submenu>
             <el-submenu index="2">
               <template slot="title"><i class="el-icon-caret-right"></i>内容管理</template>
               <el-menu-item-group>
                 <el-menu-item index="2-1">分类管理</el-menu-item>
                 <el-menu-item index="2-2">内容列表</el-menu-item>
               </el-menu-item-group>
             </el-submenu>
           </el-menu>
         </el-aside>
   
         <el-container>
           <el-header style="text-align: right; font-size: 12px">
             <el-dropdown>
               <i class="el-icon-setting" style="margin-right: 15px"></i>
               <el-dropdown-menu slot="dropdown">
                 <el-dropdown-item>个人信息</el-dropdown-item>
                 <el-dropdown-item>退出登录</el-dropdown-item>
               </el-dropdown-menu>
             </el-dropdown>
           </el-header>
           <el-main>
             <!--在这里展示视图-->
             <router-view />
           </el-main>
         </el-container>
       </el-container>
     </div>
   </template>
   
   <script>
   export default {
     name: "Main"
   }
   </script>
   
   <style scoped>
   .el-header {
     background-color: #B3C0D1;
     color: #333;
     line-height: 60px;
   }
   .el-aside {
     color: #333;
   }
   </style>
   
   ```

4. 配置嵌套路由，修改router的配置文件index.js，使用children放入main中写入子模块

   ```js
   import Vue from "vue";
   import router from "vue-router";
   import Main from "../views/Main";
   import Login from "../views/Login";
   
   import userProfile from "../views/user/Profile";
   import userList from "../views/user/List";
   
   Vue.use(router);
   
   export default new router({
     routes: [
       {
         path: '/main',
         name: 'Main',
         component: Main,
         // 路由嵌套  
         children: [
           {path: '/user/profile', component: userProfile},
           {path: '/user/list', component: userProfile}
         ]
       },
       {
         path: '/login',
         name: 'Login',
         component: Login
       }
     ]
   })
   ```

5. 效果图

   进入的时候

   ![image-20221102094146093](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102094146093.png)

   点击login之后

   ![image-20221102094210176](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102094210176.png)

   点击首页以及用户列表

   ![image-20221102094237349](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102094237349.png)

   

   



## 十二、参数传递

想要点击个人信息传递参数（模拟）



**传统传递参数的方式**

1. 对Main.vue进行修改

   此时我们在Main.vue中的route-link位置处 to 改为了 :to，是为了将这一属性当成对象使用，注意 router-link 中的 name 属性名称 一定要和 路由中的 name 属性名称 匹配，因为这样 Vue 才能找到对应的路由路径；

   ```vue
   ..\\
   <!--name：传组件名 params：传递参数，需要绑定对象：v-bind-->
   <router-link v-bind:to="{name: 'userProfile', params: {id: 1}}">个人信息</router-link>
   \\..
   ```

2. 修改路由配置

   ```js
   {	// 要携带的参数直接在路径后面写上  /:参数
       path: '/user/profile/:id', 
       name: 'userProfile', 
       component: userProfile}
   ```

3. Profile组件的修改

   ```vue
   <!--注意：{{$route.params.参数}}必须要写在<div></div>内部-->
   <template>
     <div>
       <h1>个人信息</h1>
       <h1>{{$route.params.id}}</h1>
     </div>
   
   </template>
   
   <script>
   export default {
     name: "Profile"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

4. 效果图

   ![image-20221102101543278](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102101543278.png)

   





**通过props解耦的方式实现参数传递**

1. Main.vue与传统方法一直

   ```vue
   ..\\
   <!--name：传组件名 params：传递参数，需要绑定对象：v-bind-->
   <router-link v-bind:to="{name: 'userProfile', params: {id: 1}}">个人信息</router-link>
   \\..
   ```

2. 在路由配置文件index.js中开启props权限

   ```js
   {	// 要携带的参数直接在路径后面写上  /:参数
       path: '/user/profile/:id', 
       name: 'userProfile', 
       component: userProfile,
   	props: true
   }
   ```

   

3. 在Profile.vue中修改部分内容

   ```vue
   <template>
     <div>
       <h1>个人信息</h1>
       <!--2、直接取出id-->
       <h1>{{id}}</h1>
     </div>
   
   </template>
   
   <!--1、增加props属性，并且将id写入-->
   <script>
   export default {
     props: ['id'],
     name: "Profile"
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

4. 效果图

   ![image-20221102102418026](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102102418026.png)

   



## 十三、组件重定向

重定向的意思大家都明白，但 Vue 中的重定向是作用在路径不同但组件相同的情况下，比如：

1. 在路由配置文件中配置

   ```js
   {
     path: '/main',
     name: 'Main',
     component: Main,
     children: [
       {path: '/user/profile/:id', name: 'userProfile', component: userProfile, props: true},
       {path: '/user/list', component: userList}
     ]
   },
   { // 重定向路径
     path: '/goIndex',
     // 重定向目标的路径
     redirect: '/main'
   }
   ```

   ==说明：这里定义了两个路径，一个是 /main ，一个是 /goIndex，其中 /goIndex 重定向到了 /main 路径，由此可以看出重定向不需要定义组件；==

2. 在Main.vue中写上相应的路径

   ```vue
   <el-menu-item index="1-2">
     <router-link to="/user/list">用户列表</router-link>
   </el-menu-item>
   
   <!--自己加上的-->
   <el-menu-item index="1-3">
     <router-link to="/goIndex">回到首页</router-link>
   </el-menu-item>
   ```

   



## 十四、路由钩子与异步请求



### 1.登录后显示登陆用户的名字

1. 在Login.vue的方法中==（methods）==携带登陆用户的名字

   ```js
   <template>
     <div>
       <el-form ref="loginForm" :model="form" :rules="rules" label-width="80px" class="login-box">
         <h3 class="login-title">欢迎登录</h3>
         <el-form-item label="账号" prop="username">
           <el-input type="text" placeholder="请输入账号" v-model="form.username"/>
         </el-form-item>
         <el-form-item label="密码" prop="password">
           <el-input type="password" placeholder="请输入密码" v-model="form.password"/>
         </el-form-item>
         <el-form-item>
           <el-button type="primary" v-on:click="onSubmit('loginForm')">登录</el-button>
         </el-form-item>
       </el-form>
   
       <el-dialog
         title="温馨提示"
         :visible.sync="dialogVisible"
         width="30%"
         :before-close="handleClose">
         <span>请输入账号和密码</span>
         <span slot="footer" class="dialog-footer">
           <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
         </span>
       </el-dialog>
     </div>
   </template>
   
   <script>
   export default {
     name: "Login",
     data() {
       return {
         form: {
           username: '',
           password: ''
         },
   
         // 表单验证，需要在 el-form-item 元素中增加 prop 属性
         rules: {
           username: [
             {required: true, message: '账号不可为空', trigger: 'blur'}
           ],
           password: [
             {required: true, message: '密码不可为空', trigger: 'blur'}
           ]
         },
   
         // 对话框显示和隐藏
         dialogVisible: false
       }
     },
     methods: {
       onSubmit(formName) {
         // 为表单绑定验证功能
         this.$refs[formName].validate((valid) => {
           if (valid) {
             // 使用 vue-router 路由到指定页面，该方式称之为编程式导航
             this.$router.push("/main/"+this.form.username);
           } else {
             this.dialogVisible = true;
             return false;
           }
         });
       }
     }
   }
   </script>
   
   <style scoped>
   .login-box {
     border: 1px solid #DCDFE6;
     width: 350px;
     margin: 180px auto;
     padding: 35px 35px 15px 35px;
     border-radius: 5px;
     -webkit-border-radius: 5px;
     -moz-border-radius: 5px;
     box-shadow: 0 0 25px #909399;
   }
   
   .login-title {
     text-align: center;
     margin: 0 auto 40px auto;
     color: #303133;
   }
   </style>
   
   
   ```

2. 配置路由配置文件index.js

   ```js
   {// 开启参数传递以及将参数写入路径中
     path: '/main/:name',
     name: 'Main',
     component: Main,
     props: true,
     children: [
       {path: '/user/profile/:id', name: 'userProfile', component: userProfile, props: true},
       {path: '/user/list', component: userList}
     ]
   },
   ```

3. 在Main.vue中进行配置

   ```vue
   ..
   <!--2、直接取出name-->
   <span>{{name}}</span>
   ..
   
   <!--1、增加props属性，并且将id写入-->
   <script>
   export default {
     name: "Main",
     props: ['name']
   }
   </script>
   ..
   ```

4. 效果图

   ![image-20221102110737221](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102110737221.png)

   

### 2. 路由模式和404

#### 1. 路由模式

​	==默认为hash模式==

- hash：路径带 # 符号，如 http://localhost/#/login
- history：路径不带 # 符号，如 http://localhost/login

修改路由配置index.js

```js
export default new router({
  // 通过mode属性进行修改
  mode: "history",
  routes: [
    {
      ../
  ]
```

效果图

![image-20221102111708531](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102111708531.png)

#### 2. 编写404页面

- 创建NotFound.vue

  ```vue
  <template>
  <h1>404，你的页面已经到火星了~</h1>
  </template>
  
  <script>
  export default {
    name: "NotFound"
  }
  </script>
  
  <style scoped>
  
  </style>
  ```

- 在路由配置文件中导入并且配置

  ```js
  import NotFound from "../views/NotFound";
  
  export default new router({
  
    mode: "history",
    routes: [
      {
        path: '*',
        component: NotFound
      }
    ]
  })
  ```

- 效果

  ![image-20221102112239255](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102112239255.png)



### 3. 钩子函数

`beforeRouteEnter`：在进入路由前执行
`beforeRouteLeave`：在离开路由前执行

在Profile.vue中写:

```js
export default {
  props: ['id'],
  name: "Profile",

  // 作用类似过滤器
  beforeRouteEnter:(to,from,next)=>{
      console.log('进入路由之前！');
      // 指向下一个
      next();
  },
  beforeRouteLeave:(to,from,next)=>{
      console.log('离开路由之后！')
    // 指向下一个
    next();
  }

}
```

在页面的控制台进行测试：点击个人信息以及点击其他部分进行观察

==参数说明：==

to：路由将要跳转的路径信息
from：路径跳转前的路径信息
next：路由的控制参数
next() 跳入下一个页面
next(’/path’) 改变路由的跳转方向，使其跳到另一个路由
next(false) 返回原来的页面
**next((vm)=>{}) 仅在 beforeRouteEnter 中可用，vm 是组件实例**





### 4.在钩子函数中使用异步请求

1. 安装axios

   ```
   cnpm install --save vue-axios
   ```

2. 准备数据 ： 只有**我们的 static 目录下的文件是可以被访问到的**，所以我们就把静态文件放入该目录下。
   数据和之前用的json数据一样 需要的去上述axios例子里

   ```
   // 静态数据存放的位置
   static/mock/data.json
   ```

3. main.js引用 Axios

   ```
   import axios from 'axios'
   import VueAxios from 'vue-axios'
   Vue.use(VueAxios, axios)
   ```

4. 在 beforeRouteEnter 中进行异步请求

   Profile.vue

   ```vue
   <template>
     <div>
       <h1>个人信息</h1>
       <h1>{{id}}</h1>
     </div>
   
   </template>
   
   <script>
   export default {
     props: ['id'],
     name: "Profile",
   
     // 作用类似过滤器
     beforeRouteEnter:(to,from,next)=>{
         console.log('进入路由之前！');
         // 进入路由之前执行getData方法
         next(vm =>{
           vm.getData();
         });
     },
     beforeRouteLeave:(to,from,next)=>{
         console.log('离开路由之后！')
       // 指向下一个
       next();
     },
   
     methods: {
       getData: function () {
         this.axios({
           method: 'get',
           url: 'http://localhost:8080/static/mock/data.json',
         }).then(resp=>(console.log(resp)))
       }
     }
   }
   </script>
   
   <style scoped>
   
   </style>
   ```

5. 执行

   ![image-20221102133938945](C:\Users\mudao.wang\AppData\Roaming\Typora\typora-user-images\image-20221102133938945.png)

