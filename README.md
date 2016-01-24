# 纯CSS3实现选项卡效果

border做三角形的原理

- （1）先设置witdh=0,height=0,那么div里面就不会显示任何东西
- （2）利用border-width来画一个正方形，这个正方形是由4个三角形组成的
- （3）把不需要的另外三边设置为透明就可以了

比如

        div{
			content: "";
		    width:0;
		    height: 0;
		    border: 20px solid transparent;
		    border-bottom-color:red ;
        }

###HTML5中添加自定义属性，推荐使用data-开头来做；

比如

	data-icon="H"

添加一个data-icon="H"的组定义属性

###radio的name必须一样，否则就多选了；
	<div id="table">
	    <a href="#">111</a>
	    <input type="radio" checked="checked" name="tongyi"/>
	    <a href="#" >222</a>
	    <input type="radio" name="tongyi"/>
	    <a href="#">333</a>
	    <input type="radio" name="tongyi"/>
	    <a href="#">444</a>
	    <input type="radio" name="tongyi"/>
	    <a href="#">555</a>
	    <input type="radio" name="tongyi"/>
	</div>
###checked的选择

	#table .bottom-div li input:checked + a{ background: orangered; } 

### backface-visibility定义元素不面向屏幕时候是否可见；

	backface-visibility:visible|hidden;

取值说明；

- visible：背面是可见的；
- hidden：背面是不可见的；

###transition和animation的区别

animation是一进来就有的动画；

transition是有事件触发的动画（比如鼠标点击等）

animation的写法

	animation:动画名字 持续时间 播放形式 延时时间 动画播放次数 是否轮流反向播放 ;

	动画名字需要绑定到选择器的@-webkit-keyframes;

	backwards 这个也是里面的属性；大小是动画的开始状态

下面是例子

	#input-flag5:checked ~ .table-body #flag5 h2{
	    -webkit-animation: moveDown 0.5s ease-in-out 0.3s backwards;
	    -moz-animation: moveDown 0.5s ease-in-out 0.3s backwards;
	    -ms-animation: moveDown 0.5s ease-in-out 0.3s backwards;
	    -o-animation: moveDown 0.5s ease-in-out 0.3s backwards;
	    animation: moveDown 0.5s ease-in-out 0.3s backwards;
	}
	@-webkit-keyframes moveDown{
	    0%{  -webkit-transform: translateY(-40px);  opacity: 0;  }
	    100%{  -webkit-transform: translateY(0);  opacity: 1;  }
	}


###CSS选择器的规范

.table-body和#input-flag1在同一级别，.table-body-list是属于.table-body的子元素；

这个时候

	#input-flag1:checked ~ .table-body .table-body-list h2,
上面的写法是正确的；下面的写法就是不正确的；

	#input-flag1:checked ~  .table-body-list h2,

当使用兄弟选择器的时候，+/~后面的元素一定是前面的兄弟元素；这个兄弟元素的不能省略的；

##自适应代码注意

	@media (min-width: 768px){ //>=768的设备 }
	@media (min-width: 992px){ //>=992的设备 }
	@media (min-width: 1200){ //>=1200的设备 }
我们用min-width时，小的放上面大的在下面，同理如果是用max-width那么就是大的在上面，小的在下面

	@media (max-width: 1199){ //<=1199的设备 }
	@media (max-width: 991px){ //<=991的设备 }
	@media (max-width: 767px){ //<=768的设备 }

下面是

	@media screen and (min-width: 960px) and (max-width: 1199px)
代码中用到了 screen这里指定了显示器为显示设备，也可以是print打印机等其他设备，一般我们用screen。或者干脆省略。 