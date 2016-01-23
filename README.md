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

