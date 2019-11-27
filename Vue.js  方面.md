## Vue.js  方面：

1.**Vue的核心思想：**

> 组件化开发和数据驱动。

2.**什么是vuex?有什么作用？**

> vuex是vue的状态管理工具。
>
> 作用：项目数据状态的集中管理，复杂组件的数据通信问题。

3.**Vuex的核心属性：**

> State:存储数据状态的地方，但是不可以直接修改里面的数据。
>
> Mutations: mutations定义的方法动态修改vuex的store中的状态或数据。
>
> Actions:简单的说就是异步操作数据，view层通过store.dispatch来分发action。
>
> Getters:类似vue的计算属性，主要用来过滤数据。
>
> Modules:模块化管理   项目特别复杂的时候，可以让每一个模块拥有自己的state,mutation,action,getters，使得结构非常清晰，方便管理。

4.**vuex的工作流程？**

> 在vue组件里面，通过dispatch来触发actions提交修改数据的操作
>
> 然后再通过actions的commit来触发mutations来修改数据
>
> Mutations接收到commit的请求，就会自动通过mutate来修改state里面的数据
>
> 最后由store触发每一个调用它的组建的更新。

5.**vue常用的指令？**

> V-model   v-html   v-text  v-for  v-show  v-if  v-on

6.**V-if和v-show的区别？**

> V-if是通过添加和删除DOM节点来控制显示隐藏，v-show是通过操作css的display属性来控制显示隐藏；
>
> V-if拥有更高的切换成本，v-show拥有更高的渲染成本。
>
> 频繁切换的时候使用v-show,不经常切换就使用v-if.

7.**V-for和v-if的优先级？**

> 当它们处于同一节点，v-for的优先级比v-if更高，这意味着v-if将分别重复运行于每个v-for的循环中。

8.**MVC   MVP   MVVM的区别？**

> **MVC:** MVC之间的数据通信都是单向的。View(视图层)发送指令到controller(控制层)，完成业务逻辑后，要求Model(模型层)改变状态，匠心的数据发送到(view)视图层，用户得到反馈。
>
> **MVP:**在MVP中，view和model之间没有任何通信关系，所有的通信和业务逻辑都放在presenter层中。View层发送指令到presenter层，presenter层处理业务逻辑，要求model层改变状态，完成状态修改之后，发送指令到presenter层，之后再通知view层做出改变。
>
> **MVVM:** 
>
> - Model专门用来处理数据模型，即可以在model中定义   数据修改和操作    的业务逻辑。
> - View专门用来处理用户视图，它负责将数据模型转化成UI展现出来。
> - 在MVVM架构下，View 和 Model 之间并没有直接的联系，而是通过ViewModel进行交互，Model 和 View 之间的交互是双向的， 因此View 数据的变化会同步到Model中，而Model 数据的变化也会立即反应到View 上。
> - ViewModel 通过双向数据绑定把 View 层和 Model 层连接了起来，而View 和 Model 之间的同步工作完全是自动的，无需人为干涉，因此开发者只需关注业务逻辑，不需要手动操作DOM, 不需要关注数据状态的同步问题，复杂的数据状态维护完全由 MVVM 来统一管理。
> - defiene property   
> - 发布订阅模式
> - 事件监听

9.**什么是axios?**

> 就是请求后台资源的模块，前台通过它获取后台数据，类似ajax交互。

10.**路由传参的方法？**[路由传参方法](https://links.jianshu.com/go?to=https%3A%2F%2Fsegmentfault.com%2Fa%2F1190000012393587%3Futm_source%3Dtag-newest)

> \1. 字符串拼接 ： 路由后面直接拼接要传递的参数，用this.$rote.params   接收。
>
> \2. path和query：path后面跟要跳转的路由，query后边跟要传递参数的对象   用    this.$route.query   接收。
>
> \3. name和params：name后面跟要跳转路由的名称，params后面跟传递参数的对象，用this.$route.params接收。

11.**Vuex中actions和mutations的区别？**

> Mutations的更改是同步更改，用于用户执行直接数据更改，this.$store.commit(‘名’)触发。
>
> Actions的更改是异步操作，用于需要与后端交互的数据更改,this.$store.dispath(“名”)触发。
>
> 注意：
>
> 1)：定义actions方法创建一个更改函数时，这个函数必须携带一个context参数，用于触发mutations方法，context.commit(‘修改函数名’ , ’异步请求值’)；
>
> 2)：mutations第一个参数必须传入state，第二个参数是新值。

12.**渐进式框架的理解？**

> 主张最少，没有多做职责之外的事         我的理解就是    用什么就引入什么，没有硬性规定。

13.**构建的 vue-cli 工程都到了哪些技术，它们的作用分别是什么？**

>1. vue.js：vue-cli工程的核心，主要特点是 双向数据绑定 和 组件系统。
>2. vue-router：vue官方推荐使用的路由框架。
>3. vuex：专为 Vue.js 应用项目开发的状态管理器，主要用于维护vue组件间共用的一些 变量 和 方法。
>4. axios（ 或者 fetch 、ajax ）：用于发起 GET 、或 POST 等 http请求，基于 Promise 设计。
>5. vux等：一个专为vue设计的移动端UI组件库。
>6. 创建一个emit.js文件，用于vue事件机制的管理。
>7. webpack：模块加载和vue-cli工程打包器。

14.**请你详细介绍一些 package.json 里面的配置**

>常用对象解析
>
>1. scripts：npm run xxx 命令调用 node 执行的 .js 文件
>2. dependencies：生产环境依赖包的名称和版本号，即这些 依赖包 都会打包进 生产环境的JS文件里面
>3. devDependencies：开发环境依赖包的名称和版本号，即这些 依赖包 只用于 代码开发 的时候，不会打包进 生产环境js文件 里面。

15.**vue-cli如何新增自定义指令**

1.创建局部指令

```js
var app = new Vue({
   el: '#app',
   data: {    
   },
   // 创建指令(可以多个)
   directives: {
       // 指令名称
       dir1: {
           inserted(el) {
               // 指令中第一个参数是当前使用指令的DOM
               console.log(el);
               console.log(arguments);
               // 对DOM进行操作
               el.style.width = '200px';
               el.style.height = '200px';
               el.style.background = '#000';
           }
       }
   }
})
```

2.全局指令

```js
Vue.directive('dir2', {
   inserted(el) {
       console.log(el);
   }
})
```

3.指令的使用

```html
<div id="app">
   <div v-dir1></div>
   <div v-dir2></div>
</div>
```

16.**什么是vue生命周期**

```js
Vue 实例从创建到销毁的过程，就是生命周期。从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、销毁等一系列过程，称之为 Vue 的生命周期。
```

17.**vue生命周期的作用是什么**

```js
它的生命周期中有多个事件钩子，让我们在控制整个Vue实例的过程时更容易形成好的逻辑。
```

18.**第一次页面加载会触发哪几个钩子**

```js
会触发 beforeCreate, created, beforeMount, mounted
```

19.**vue生命周期**

```js
8个阶段(它可以总共分为8个阶段：创建前/后, 载入前/后,更新前/后,销毁前/销毁后)

注： [ DOM 渲染在 mounted 中就已经完成了 ]

1.beforeCreate（创建前）
    1）在数据观测和初始化事件还未开始,
    2）vue实例的挂载元素$el和数据对象data都为undefined
2.created（创建后）     
    1）完成数据观测，属性和方法的运算，
    2）初始化事件,vue实例的数据对象data有了,
    3）但是挂载元素$el属性还没有显示出来
3.beforeMount（载入前） 
    1）在挂载开始之前被调用，
    2）相关的render函数首次被调用。
    3）实例已完成以下的配置：编译模板，把data里面的数据和模板生成html。
    4）注意此时还没有挂载html到页面上,vue实例的$el和data都初始化了，但还是挂载之前为虚拟的dom节点，data.message还未替换。
4.mounted（载入后） 
    1）在el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用。
    2）实例已完成以下的配置：用上面编译好的html内容替换el属性指向的DOM对象。
    3）完成模板中的html渲染到html页面中,vue实例挂载完成，data.message成功渲染。
    4）此过程中进行ajax交互。
5.beforeUpdate（更新前） 
    1）在数据更新之前调用，发生在虚拟DOM重新渲染和打补丁之前。
    2）可以在该钩子中进一步地更改状态，不会触发附加的重渲染过程。
6.updated（更新后） 
    1）在由于数据更改导致的虚拟DOM重新渲染和打补丁之后调用。
    2）调用时，组件DOM已经更新，
    [所以可以执行依赖于DOM的操作。]
    [然而在大多数情况下，应该避免在此期间更改状态，因为这可能会导致更新无限循环。]
    3）该钩子在服务器端渲染期间不被调用。
7.beforeDestroy（销毁前） 
    1)在实例销毁之前调用。
    2)实例仍然完全可用。
8.destroyed（销毁后） 
    1)在实例销毁之后调用。
    2)调用后，所有的事件监听器会被移除，所有的子实例也会被销毁。
    3)该钩子在服务器端渲染期间不被调用。
```

20.**vue实现数据双向绑定的原理：Object.defineProperty()**

```js
vue实现数据双向绑定主要是:
    1.采用  数据劫持  结合  发布—订阅模式  的方式，
    2.通过Object.defineProperty（）来劫持各个属性的setter，getter，在数据变动时发布消息给订阅者，触发相应监听回调。
```

21.**vue组件间的参数传递**

```js
1.父组件与子组件传值
    父组件传给子组件：子组件通过props方法接受数据;
    子组件传给父组件：$emit方法传递参数
2.非父子组件间的数据传递，兄弟组件传值
    eventBus，就是创建一个事件中心，相当于中转站，可以用它来传递事件和接收事件。项目比较小时，用这个比较合适。（虽然也有不少人推荐直接用VUEX，具体来说看需求咯。技术只是手段，目的达到才是王道。）
```

22.**vue的路由实现：hash模式和history模式**

```jade
1.hash模式
 1）在浏览器中符号“#”，#以及#后面的字符称之为hash，用window.location.hash读取；
 2）//特点：hash虽然在URL中，但不被包括在HTTP请求中；
         用来指导浏览器动作，对服务端安全无用，hash不会重加载页面。
 3）hash 模式下，仅 hash 符号之前的内容会被包含在请求中；
    //因此对于后端来说，即使没有做到对路由的全覆盖，也不会返回 404 错误。  
2.history模式
  1)history采用HTML5的新特性；
  2)且提供了两个新方法：
    pushState（），replaceState（）可以对浏览器历史记录栈进行修改，以及popState事件的监听到状态变更。
  3）history 模式下，前端的 URL 必须和实际向后端发起请求的 URL 一致；
    后端如果缺少对 /items/id 的路由处理，将返回 404 错误。
    [ue-Router 官网里如此描述：“不过这种模式要玩好，还需要后台配置支持……所以呢，你要在服务端增加一个覆盖所有情况的候选资源：如果 URL 匹配不到任何静态资源，则应该返回同一个 index.html 页面，这个页面就是你 app 依赖的页面。”]
```

23.**vue与angular以及react的区别(待完善)**

```
1.与AngularJS的区别
    相同点：
        都支持指令：内置指令和自定义指令；
        都支持过滤器：内置过滤器和自定义过滤器；
        都支持双向数据绑定；
        都不支持低端浏览器。
     不同点：
        AngularJS的学习成本高，比如增加了Dependency Injection特性，而Vue.js本身提供的API都比较简单、直观；
        在性能上，
        AngularJS依赖对数据做脏检查，所以Watcher越多越慢；           Vue.js使用基于依赖追踪的观察并且使用异步队列更新，所有的数据都是独立触发的。
2.与React的区别

```



​          事件循环

**项目介绍1**

**项目介绍：**

**项目背景：**

**商品分类怎么实现的;**

**单选多选全选怎么实现的：**

**加入购物车怎么实现的;**

**登录注册怎么实现;**

**登录流程：**

> ​        当我点击登录的时候，我先判断我输入的值是否符合规则，如果符合，就把参数拼接到接口上，然后请求，后台会返回一个token值，我把token放在本地存储中，在全局路由守卫中，当我要访问一个需要登录才可以进入的路由的时候，我就判断本地存储中有没有这个token值，如果有，就进入这个路由，如果没有，就返回登录页面登录。

**Loading动画怎么实现：**

> ​        用axios拦截器实现loading动画效果      首先新建一个loading组件，里面写一些动画效果，然后在vuex里面写一个状态来控制我的loading动画组件的显示隐藏，然后在全局main.js中配置axios拦截器，分别定义一个请求拦截器和响应拦截器，在请求数据时执行请求拦截器，改变我vuex里面定义的状态，让loading动画显示，反之，数据请求到之后，隐藏loading动画即可。

**图片懒加载怎么实现：**

> ​        我们先不给<img>设置src，把图片真正的URL放在另一个属性data-src中，在需要的时候也就是图片进入可视区域的之前，将URL取出放到src中。

**移动端的性能优化：**

> ​         首屏加载和按需加载，懒加载	资源预加载	图片压缩处理，使用base64内嵌图片	合理缓存dom对象	使用touchstart代替click（click 300毫秒的延迟）	利用transform:translateZ(0)，开启硬件GUP加速	不滥用web字体，不滥用float（布局计算消耗性能），减少font-size声明	使用viewport固定屏幕渲染，加速页面渲染内容	尽量使用事件代理，避免直接事件绑定。

**项目介绍2**

**项目介绍：**

**项目背景：**

**后台权限管理是怎么实现的：**

> ​       定义两张路由表，一张是静态路由表（无需权限的使用），另一张是权限路由表（和后台返回的权限进行匹配使用）。用户登录，判断登录是否成功，登录成功后判断是否获取用户权限列表，获取到后，将权限数据存储到Vuex中。用Vuex中的权限数据和定义好的需要访问权限的路由表进行比对。比对完后生成当前账户对应的权限路由表。通过addRouters方法动态添加路由规则，生成可访问的侧边栏菜单。

**跨域问题，怎么解决的：**

> **jsonp跨域原理：** jsonp是请求之后  后台会封装好的一段json，并且把数据放在一个callback回调函数中，并返回一个js文件，动态的引入这个文件，调用这个callback回调函数，进行数据访问。
>
> **反向代理跨域：**客户端发送请求时不直接到服务器而是先到代理的中间层在这里将localhost：8080的这个域名装换为www.njc.com，再将请求发送到服务器这样在服务器端收到的请求就是使用的www.njc.com域名同理，当服务器返回数据的时候，也是先到代理的中间层将www.njc.com转换成localhos：8080；这样在客户端也是在相同域名下访问的了。