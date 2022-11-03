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

   ![image-20221028133842859](.\typora-user-images\image-20221028133842859.png)

3. 在控制台上修改后的效果图

   ![image-20221028134220216](.\typora-user-images\image-20221028134220216.png)





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

![image-20221028141610084](.\typora-user-images\image-20221028141610084.png)

**提示信息为hello vue**



在Console上进行修改

![image-20221028142119998](.\typora-user-images\image-20221028142119998.png)



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



![image-20221028143253926](.\typora-user-images\image-20221028143253926.png)

在Console上进行修改

![image-20221028143336076](.\typora-user-images\image-20221028143336076.png)







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

![image-20221028143911514](.\typora-user-images\image-20221028143911514.png)





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

![image-20221028151323525](.\typora-user-images\image-20221028151323525.png)

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

![image-20221028151521924](.\typora-user-images\image-20221028151521924.png)





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

  ![image-20221028160047230](.\typora-user-images\image-20221028160047230.png)

  在文本中输入其他数字和字符会同时改变

  ![image-20221028160159407](.\typora-user-images\image-20221028160159407.png)







- textarea场景

  ![image-20221028160614747](.\typora-user-images\image-20221028160614747.png)

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

  ![image-20221028161451673](.\typora-user-images\image-20221028161451673.png)

  ![image-20221028161524069](.\typora-user-images\image-20221028161524069.png)

  





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

![image-20221031111033165](.\typora-user-images\image-20221031111033165.png)



==json文件的格式==

![image-20221031111240492](.\typora-user-images\image-20221031111240492.png)











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

![image-20221031114159605](.\typora-user-images\image-20221031114159605.png)

- 点击“点我”跳转到"https://www.baidu.com"









## 在Leecode刷题

1. 1. 罗马数字转整数

      ```java
      class Solution {
          // 使用HashMap存储数据
          Map<Character, Integer> map = new HashMap<Character, Integer>();
              map.put('I', 1);
              map.put('V', 5);
              map.put('X', 10);
              map.put('L', 50);
              map.put('C', 100);
              map.put('D', 500);
              map.put('M', 1000);
              
          public int romanToInt(String s) {
              int sum = 0;
              int len = s.length() - 1;
              for (int i = len; i >= 0; i--) {
              	// temp用于存放当前的罗马数字代表的值
                  int temp = map.get(s.charAt(i)); 
                  // 解决除了最后一个值以外小的数在左边的情况
                  if (i != len && map.get(s.charAt(i + 1)) > temp) {
                      sum -= temp;
                  } else {
                      // 罗马数字的顺序正常则转换后再相加
                      sum += temp;
                  }
              }
              return sum;
          }
      }
      ```

      
