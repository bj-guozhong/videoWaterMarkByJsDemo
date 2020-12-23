# videoWaterMarkByJsDemo
为Projekktor视频播放控件增加页面水印效果

Desc:项目需求从CMS接口获取到视频信息进行展示，视频本身不带水印，在显示视频的时候需要简单的加个水印，为此修改了下播放器源码以实现全屏水印效果。

Update by gz 20201221

1.加入watermark3()方法，该方法用于在全屏显示时加文字水印效果,watermark3()方法来源src="water3.js",正常情况下参数为当前登陆人工号和姓名，如传"clear"则清空在全屏显示的水印，即取消全屏;

全屏和取消全屏事件需要在projekktor.min.js源码中修改;

2.左上角显示的logo水印可进行自行替换;

3.为了右键不显示自带的广告，去掉mouseleaveHandler:function()之前的如下代码：
mousedownHandler:function(e){console.log("mouse999");switch(e.which){case 3:var i=this.pp.getDC().offset(),s=e.pageY-i.top,n=e.pageX-i.left;n+this._dest.width()>this.pp.getDC().width()&&(n=this.pp.getDC().width()-this._dest.width()-2),s+this._dest.height()>this.pp.getDC().height()&&(s=this.pp.getDC().height()-this._dest.height()-2),this.setActive(),this._dest.css({top:s+"px",left:n+"px"});break;case 1:try{this._items[t(e.target).data("plugin")].open()}catch(a){}default:this.setInactive()}}

3.注意:尽量不要格式化JS源文件,网上有一些格式化JS文件的工具，格式化之后不能正常运行。

4.下载源码可直接运行demo.html进行展现或扩展。

非全屏效果图：
https://github.com/bj-guozhong/repositoryvideoWaterMarkByJsDemo/raw/main/img/not_fullscreen.png

全屏效果图：
https://github.com/bj-guozhong/repositoryvideoWaterMarkByJsDemo/raw/main/img/fullscreen.png
