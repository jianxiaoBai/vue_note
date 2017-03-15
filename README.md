## 基础使用

**class使用方式:**

- 对象语法
	- v-bind:class="{ '类名-a': 布尔值, '类名-b': 布尔值 }"
- 数组语法
	- v-bind:class="[classA, classB]"
		- data: {classA: '类名-a',classB: '类名-b'}
	- v-bind:class="[classA, isB ? classB : '']"  （三元表达式）

**style使用方式:**

 - 对象语法
	 -  `<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px'}><div>`
		 -  `data: {activeColor: 'red',fontSize: 30}`
	 -  推荐  `<div v-bind:style="styleObject"></div> `
- 数组语法
	- `<div v-bind:style="[styleObjectA, styleObjectB]">`

**循环的用法:**

>在循环中添加 <li v-for="val in arr" `:key="$index"`>  提升循环性能

- 对象
	- <li v-for="(v,k) in obj"></li> 

- 数组
	- <li v-for="val in arr"></li> 

**绑定事件的2种方式:**

1.  v-on:click="fn( )";
2.  @click="fn( )"  ` 推荐`

**属性的绑定:**

- v-bind:src=""   （src可写成   width/height/title 等等 ）
- :src=""    推荐

**模板的几种使用方法:**

- {{msg}}         数据更新模板变化
- {{*msg}}       数据只绑定一次
- {{{msg}}}      HTML转意输出


**事件对象: （事件发生时触发的对象，对象里有各种信息）**

- @click="fn($event)"   
	- 传入形参，必须是 $event

**阻止冒泡的俩种方式: **
- ev.cancelBubble=true;    原声写法
- @click.stop                    `推荐`

**阻止默认行为的俩种方式(默认事件):**

- ev.preventDefault();
- @contextmenu.prevent    `推荐`

**监听数据变化**

- 浅度监听
	- Vm.$watch(name,fnCb);                    
- 深度监听（也就是可以监视 复杂嵌套数据的变化）
	- vm.$watch(name, fnCb,{deep:true});  

**防止花括号闪烁**

1. 此方法一般会用在比较大的段落，也就是段落中 {{ }} 比较多的地方
	- 在使用花括号的父元素设置 v-cloak 属性
	- 在样式设置  [v-cloak]{ display: none; }
2. `<span v-html="msg"></span>`   `推荐`


**一些实例的简单方法**

- vm.$el      就是那个元素
- vm.$data  就是那个data对象
- vm.$destroy  破坏（销毁）对象 
- vm.$log()    查看现在data对象里面数据的状态
- vm.$mount 手动安装 （挂载）
	- ![](https://github.com/jianxiaoBai/vue_note/raw/master/imgs/mount.png)

- vm.$options 自定义属性
	- ![](https://github.com/jianxiaoBai/vue_note/raw/master/imgs/options.png)

