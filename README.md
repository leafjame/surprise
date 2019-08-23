# 🌹🌹🌹

# 背景

最近在整理自己的电脑，无意间发现了这个文件夹，最后修改时间停留在`2015`年。

打开后才知道，这是当年自己不知道在哪里看到的，觉得好玩就下载留存了，当时只有单独的**一个文件**：`rose.html`。

> 记不得文件来源及作者了，这是向原创者表示感谢。（有知情者也可留言）

# 效果

**（解压即所得）**

![image](http://pwfvtet6u.bkt.clouddn.com/rose1.gif)

最开始的时候，页面里只有一朵玫瑰花。也就是在几年前，我在里面加了其他的元素，最终发给女神，给惊呆了😜😜😜

# 修改明细
代码很简单，只依赖jQuery。所加的功能都是自己刚接触js前端不久，学着加上去的，现在看看觉得`好low`啊。。。😂。。效果凑合着看吧，谁叫女神不懂呢~

## 1、歌曲播放

左上角的歌曲播放，当时要做`上一曲`、`下一曲`的，可惜没有实现，只做到随机播放，依赖于刷新网页

```
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
> 歌曲还是写死的。。。😝。。当时针对IE和其他浏览器做了测试

## 诗句
找了两首诗，其中一首是网上直接能搜到的，另一首是拼凑的`藏头诗`，外加一些变色效果。。

## 游动文字
首尾各加了一些游动文字效果，简单的`html标签` 加 `js`实现

## 分享功能
当时做这个是为了方便女神分享到朋友圈什么的，不过由于是本地文件，分享效果不是很理想。。。

# 写在最后

有兴趣的小伙伴，可尝试着改成你们喜欢的样子哦~

__**欢迎讨论**__~~~ 🌹🌹🌹

