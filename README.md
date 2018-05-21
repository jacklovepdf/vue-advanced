
开启我学习vue之旅；


1.数据绑定（数据绑定到DOM文本或特性，还可以绑定到DOM结构。）
(1).模版数据的绑定
    双大括号会将数据解释为普通文本，
```javascript
    <div id="app">
      {{ message }}
    </div>
    var app = new Vue({
      el: '#app',
      data: {
        message: 'Hello Vue!'
      }
    })
```

(2).元素特性绑定
    以v-开头的表示vue的指令，v-bind绑定特性之后，特性的值可以是data中的变量；
```javascript
    <div id="app-2">
      <span v-bind:title="message">
        1111111
      </span>
    </div>
    var app2 = new Vue({
      el: '#app-2',
      data: {
        message: '日期为：' + new Date().toLocaleString()
      }
    })
```

(3).条件与循环（绑定dom结构）
   根据组件的特性（属性）值控制组件是否展示

```javascript
    <div id="app-3">
      <p v-if="seen">现在你看到我了</p>
    </div>
    var app3 = new Vue({
      el: '#app-3',
      data: {
        seen: true
      }
    })
```

```javascript
    <div id="app-4">
      <ol>
        <li v-for="todo in todos">
          {{ todo.text }}
        </li>
      </ol>
    </div>
    var app4 = new Vue({
      el: '#app-4',
      data: {
        todos: [
          { text: '学习 JavaScript' },
          { text: '学习 Vue' },
          { text: '整个牛项目' }
        ]
      }
    })
```

2. 事件绑定

    用v-on指令添加一个事件监听器；

```javascript
    <div id="app-5">
      <p>{{ message }}</p>
      <button v-on:click="reverseMessage">逆转消息</button>
    </div>
    var app5 = new Vue({
      el: '#app-5',
      data: {
        message: 'Hello Vue.js!'
      },
      methods: {
        reverseMessage: function () {
          this.message = this.message.split('').reverse().join('')
        }
      }
    })
```

3.数据双向绑定
表单输入和应用状态之间的双向绑定；

```javascript
    <div id="app-6">
      <p>{{ message }}</p>
      <input v-model="message">
    </div>
    var app6 = new Vue({
      el: '#app-6',
      data: {
        message: 'Hello Vue!'
      }
    })
```

4.组件
   一个Vue应用由一个通过new Vue创建的根Vue实例，以及可选的嵌套的、可复用的组件树组成
（4.1）组件数据与方法
    当一个 Vue 实例被创建时，它向Vue的响应式系统中加入了其data对象中能找到的所有的属性。
当这些属性的值发生改变时，视图将会产生“响应”。
    除了用户定义的数据属性之外，Vue 实例还暴露了一些有用的实例属性与方法；
    https://cn.vuejs.org/v2/api/#%E5%AE%9E%E4%BE%8B%E5%B1%9E%E6%80%A7;
（4.2）组件的生命周期
    每个Vue实例在被创建时都要经过一系列的初始化过程——例如，需要设置数据监听、编译模板、将实例挂载到DOM并在数据变化时更新DOM等。
    同时在这个过程中也会运行一些叫做生命周期钩子的函数，这给了用户在不同阶段添加自己的代码的机会。
    https://cn.vuejs.org/v2/guide/instance.html

    create-->mount-->update-->destroyed


5.模版语法
  Vue.js使用了基于HTML的模板语法，允许开发者声明式地将DOM绑定至底层Vue实例的数据。


