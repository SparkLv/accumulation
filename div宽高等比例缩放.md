设置宽高比在很多时候是有用的。

我们设置一个容器的宽高比为16:9

//HTML代码片段
```
<div class="container">
      <div class="wrapper">
         <div class="content">content</div>
      </div>
    </div>
```
//css 代码
```
div{
    border: 1px solid green;
    }
.container{ 
    width:400px;
    }
.wrapper{
    position:relative;
    padding-top:25px;
    padding-bottom:56.25%;   // 16/9 = 0.5625;
    height:0;
    border: 1px solid red;
    }
.content{
    position:absolute;
    top: 0;
    left: 0;
    width: 100%;
    height:100%;
    background:gray;
}
```
我们看到先设置.container容器宽度为400.这个值可以使任意的宽度，也可以是一个百分比。

.wrapper容器设置了 padding-bottom为56.25% 。 这个百分比是16/9的值，这里设置padding-bottom为父容器.container的宽度的百分之56.25.

另外。设置padding-top 为25px，这里在实际中也比较有用。 比如我们要设置一个视频播放器播放界面的宽高比为16:9。我们还希望播放界面上面留下25px的高度来放置播放控制的按钮。

通过padding-bottom和padding-top撑起了.wrapper容器的高度。并且设置height为0;

接下来是.comtent元素。我们设置这个元素绝对定位。top:0,left:0; width:100%;height:100%;因为它的父元素.wrapper的宽度和高度已经成比例了，所以使用width:100%;height:100%;就让content容器达到目的了。通过改变.container的宽度，.content元素的高宽也能成比例的改变。