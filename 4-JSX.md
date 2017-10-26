### 什么是JSX
	JSX就是Javascript和XML结合的一种格式
	React发明了JSX，利用HTML语法来创建虚拟DOM。
	当遇到<,JSX就当HTML解析，遇到{,就当JavaScript解析。

### JSX --> Javascript
	JSX:ReactDOM.render(
			<h1>你好</h1>,
			document.getElementById('container')
		)
	JS: ReactDOM.render(
			React.createElement('h1',null,'你好'),
			document.getElementById('container')
		)

### JSX中运行javascript语法，用{}
	var myStyle = {
        fontSize:100,
        color:'#cccccc'
      };
    ReactDOM.render(
    <h1 style={myStyle}>我是灰色字体</h1>,
        document.getElementById('box')
     ); 
