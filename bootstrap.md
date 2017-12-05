导航
	nav 			导航
	navbar-inverse 	背景黑色
	navbar-default 	背景白色
	nav-pills 		胶囊
	navbar-collapse 所包含内容不可见
	navbar-header 	最小768px
	navbar-brand 	增加行高，字体大小
	navbar-fixed-top固定导航栏顶部
	navbar-header 	导航头部，最后存在
	navbar-right	导航向右
	
	响应式导航
		折叠内容需包括下列类名的div中
			.collapes
			.navbar-collapes
		折叠带有class.navbar-toggle .collapesd的按钮(两个属性)
			data-toggle : 做什么(折叠)
			data-target : 切换目标(带选择器)
	
	轮播
		div.carousel slide 需要ID便于绑定
			轮播指标
				<ol>
					<li data-target='#主ID' data-slide-to='索引' class='active(当前)'></li>
				</ol>
			轮播项目
				div.carousel-inner
					div.item active(当前)
						<img>
						<!-- 说明内容 -->
						<div class="carousel-caption"></div>
			左右导航
				a.left(right) carousel-control 
				  href='#主ID'
				  data-slide='prev(next)'
				  class='glyphicon glyphicon-chevron-left(right)'


快速浮动
	pull-left 左浮动
	pull-right 右浮动
