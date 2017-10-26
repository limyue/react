### native
	react模板：
		1.在使用React之前，我们必须要先引入三个库——react.js/react-dom.js/browser.min.js
		2.body内部编写JSX代码<script type="text/babel"> {/* 此处编写react编码 */}</script>

### ReactDOM.render()
	1.用于将模板转为HTML语言，并插入指定的DOM节点。
	2.JSX比较特殊的是允许Javascript和HTML的混写
	3.ReactDOM.render(template,targetDOM),
		该方法接收两个参数：第一个是创建的模板；第二个参数是插入该模板的目标位置
	4.	HTML:<div id="container"></div>
		JSX: ReactDOM.render(
				<h1>你好</h1>,
				document.getElementById('container')
			 )

### React 组件
	1.使用jsx来将代码封装成React组件，然后像插入普通 HTML 标签一样，在其他地方插入这个组件。使用React.createClass用于生成一个组件。
	2.命名规则：创建的组件类由大写字母开头，并且符合驼峰命名。
	3.每个组件必须实现自己的render方法，并且输出定义好的模块，返回值null,false,组件模板
	4.组件类只能包含一个顶层标签
	5. var HelloReact = React.createClass({
	  		render: function(){
	  			return <h1>React</h1>
	  		}
	  });
	  ReactDOM.render(
		<HelloReact />,
		document.getElementById('container')
	  )

### 组件样式 (web 组件)
	 设置组件的样式 三种：
      1、内联样式
      2、对象样式
      3、选择器样式className
	    var hStyle={
	      backgroundColor:"green",
	      color:"red"
	    }
	    var ShowMessage =React.createClass({
	      render:function(){
	        return (
	        	      <!--  1、内联样式  -->
	         	 <div style={{backgroundColor:"yellow",borderWidth:5,borderColor:"black",borderStyle:"solid"}}>
	         	      <!--  2、对象样式 -->
	            <h1 style={hStyle}>{this.props.firstRow}</h1>
	                  <!--  3、选择器样式 -->
	            <p className="pStyle">{this.props.secondRow}</p>
	          </div>
	        );
	      }
	    });
	    ReactDOM.render(
	      <ShowMessage firstRow="你好" secondRow="蓝鸥"/>,
	      document.getElementById("container")
	    );

### 复合组件
	复合组件：也被称为组合组件，创建多个组件合成一个组件

### props、state
    1.props:是组件自身的属性，一般用于嵌套的内外层组件中，负责传递信息(通常是由父层组件向子层组件传递)
    注意：props对象中的属性与组件的属性一一对应，不要去直接去修改props中属性的值
    2.this.props
		props提供的语法糖，可以将父组件中的全部属性都复制给子组件
	3.this.props.children
    	children是一个例外，它不像props一样跟组件的属性一一对应，
    	表示组件的所有子节点
    4.属性验证 propTypes
    5.getDefaultProps
    6.state属性：http://blog.csdn.net/a821814989/article/details/53812376

### 生命周期
	生命周期介绍：
    1、组件的生命周期一般可以分为三个状态：
        Mounting:组件挂载，组件渲染完成了，已插入真实DOM
        Updating:组件更新，正在被重新渲染
        Unmounting: 组件移出，已移出真实DOM
    2、组件的生命周期可以分为四个阶段：创建、实例化、更新、销毁
    		1、生命周期中与props和state相关：
		      (1)getDefaultProps 设置props属性默认值
		      (2)getInitialState 升值state属性初始值
			2、Mounting/组件挂载相关：
		      (1) componentWillMount
		         组件将要挂载。在render之前执行，但仅执行一次，即使多次重复渲染该组件，或者改变了组件的state
		      (2)componentDidMount
		         组件已经挂载，在render之后执行，同一个组件重复渲染只执行一次
		    3、Updating/组件更新相关：
		      (1)componentWillReceiveProps(object nextProps)
		         已加载组件收到新的props之前调用，注意组件初始化渲染时则不会执行
		      (2)shouldComponentUpdate(object nextProps,object nextState)
		         组件判断是否重新渲染时调用。该接口实际是在组件接收到了新的props或者新的state的时候会立即调用
		         ，然后通过
		      (3)componentWillUpdate(object nextProps,object nextState)
		         组件将要更新
		      (4)componentDidUpdate(object prevProps,object prevState)
		         组件已经更新
		    4、Unmounting/组件移除相关：
		      (1)componentWillUnmount
		         在组件要被移除之前的时间点触发，可以利用该方法来执行一些必要的清理组件将要移除
		   





