&emsp;&emsp;最近在整理自己的电脑，无意间发现了一个文件夹，最后修改时间停留在2015年。不知在哪看到的这款特效，觉得很炫就下载留存了，只有简单的一个文件：**rose.html**，已上传github，欢迎下载。（侵删)

<!--more-->

展示的效果如下：

![nOckzq.gif](https://s2.ax1x.com/2019/09/20/nOckzq.gif)

**Github下载地址：**

<a href="https://github.com/leafjame/Surprise" class="LinkCard">表白神器—JS生成的玫瑰花</a>

最开始的时候，页面里只有一朵玫瑰花。也就是在几年前，我在里面加了其他的元素，最终发给女神，给惊呆了。

代码很简单，只依赖jQuery。所加功能都是自己刚接触前端不久，学着加上去的，现在看觉得好low。。左上角的歌曲播放，当时要做上一曲、下一曲的，可惜没有实现，只做到随机播放，依赖于刷新网页。

```javascript
if(Sys.ie){
  var song = getFileName().split("|");
  for(var i=0;i<song.length;i++){
    var indexSong = song[i].lastIndexOf("\\");
    song[i] = song[i].substring(indexSong+1,song[i].length);
  }
  //得到播放曲目下标
  songIndex = parseInt(Math.random() * song.length);
  $("#audio_id").attr("src",song[songIndex]);
  //console.log(parseInt(Math.random() * song.length));
  //Math.random()是令系统随机选取大于等于 0.0 且小于 1.0 的伪随机 double 值，是Java语言常用代码。
  //例如：var a:Number=Math.random()*2+1，设置一个随机1到3的变量。
}else{
  //固定歌曲 
  var StaticSong = new Array( '张杰-My Sunshine.mp3', '朴树-平凡之路.mp3', 'Westlife-The Rose.mp3', '徐良-月光.mp3', '许嵩-七夕.mp3', '徐良-红装.mp3',
    '许嵩-弹指一挥间.mp3', '许嵩-惊鸿一面.mp3', '许嵩-山水之间.mp3', '降央卓玛-西海情歌.mp3', '降央卓玛-雨中飘荡的回忆.mp3' );　//创建一个数组并赋值
  $("#audio_id").attr("src",StaticSong[parseInt(Math.random() * StaticSong.length)]);
}
//回显曲目
$("#song_title").html($("#audio_id").attr("src"));
```
> 歌曲以前写死的。。针对IE和其他浏览器做了测试

找了两首诗，其中一首是网上直接能搜到的，另一首是拼凑的藏头诗，外加一些变色效果。
```
日高闲步下堂阶
细草春莎没绣鞋
折得玫瑰花一朵
凭君簪向凤凰钗
```
这首诗悬浮在玫瑰花正上方

![](https://s2.ax1x.com/2019/09/07/n1QGiF.md.png)

首尾各加了一些游动文字效果，简单的html标签加js实现

页面最右侧有分享功能，当时做这个是为了方便女神分享到朋友圈，不过由于是本地文件，效果不是很理想。

有兴趣的小伙伴，可尝试着改成你们喜欢的样子哦~

程序员的表白神器，你**get**到了吗~
