# day04

css: 网页的美容师

css3   动画 



## 过渡动画

两个状态  +  事件触发 (鼠标移入，鼠标点击) ---》 有时间的持续

```css
transition:要过渡属性  持续时间s  延时时间s  运动曲线(linear匀速);
```

==谁做变化写到谁身上==

如果写到元素身上，那么在事件触发完毕后回到最初状态会有时间持续

如果写到事件里，那么在事件触发完毕后回到最初状态没有持续时间 会立即回到最初状态



**常见写法:**

```css
 transition:background-color 1s 0s linear,width 2s 0s linear  ,height 3s 0s linear  ;
            /* all 只要事件里的属性全部加过渡  */
            /* transition: all 1s 0s linear; */
            /* transition: all 1s; */
            /* transition: .5s; */
```



## 变形动画

属性名字:transform 

类型：

平移 ， 缩放，旋转， 倾斜 

#### 平移

```css
transform:translate(xpx,ypx); x轴 水平方向(x轴) y轴 垂直方向

transform:translate(x%,y%);  x% 代表的是移动了自身宽度的%多少

transform:translate(-50%,0%);  向左移动了自身宽度的一半

transform:translate(0%,-50%);  向上移动了自身高度的一半
```



### 旋转（2d）

```css
transform:rotate(ndeg);  n度数  +ndeg 顺时针  -ndeg逆时针
```



### 缩放

```css
transform:scale(w,h);  w,h没有单位  缩放倍数  w>1 放大  w<1缩小  w = 0这个元素就消失

-1 反转  

transform:scaleX(-1); 水平方向上做了反转
transform:scaleY(-1); 垂直方向上做了反转
```

### 倾斜

```css
transform:skew(xdeg,ydeg);  xdeg 在x轴方向的倾斜角度  -xdeg正方向  +xdeg 负方向
```





## 3d变形

### 旋转

```css
transform:rotate3d(x,y,z,ndeg);
x x= 1 绕x轴有旋转 x= 0 在x轴方向没有旋转
y y= 1 绕y轴有旋转 y= 0 在y轴方向没有旋转
....

transform:rotate3d(1,0,0,45deg);

transform:rotate3d(0,1,0,45deg);

transform:rotate3d(0,0,1,45deg);
```





### 平移

```css

transform:translate3d(xpx,ypx,zpx);
transform:translate3d(100px,100px,0px);

transform:translateX(100px);
transform:translateY(100px);
transform:translateZ(100px);

transform:translateX(100px)  translateY(100px);
```



### 景深属性

```css
       3d 空间 近大远小----》 把眼睛拿出来  拿出屏幕 
        景深属性 : perspective:眼睛到变形物体的距离 
        默认是0px

        一般要设置变形物体的父级元素身上

        作用： 加过渡的时候看到3d效果 
```

### 保留3d属性

```css
transform-style:preserve-3d;3d效果默认一般是不保留的  只有加这个属性才能让3d效果在没有事件触发的情况下保留下来
```







## 关键帧动画

抽象成几个状态     

```css
1.定义
小球运动的动画  (W) 5个关键状态

@keyframes 动画名字 {
    //5个状态  0%--100% 
    0% {
      
    }
    25% {
       
    }
    50% {
        
    }
    75% {
        
    }
    100% {
        
    }
}


2.使用

animation:动画的名称  持续的时间s  延时时间s  运动的曲线   运动的次数(1/infinite)   是否往返 

最后一帧的状态  播放状态;


动画的名称  animation-name

 持续的时间s animation-duration

延时时间s  animation-delay

运动的曲线 animation-timing-function

运动的次数 animation-iteration-count

是否往返  animation-direction:normal(默认) / alternate反向 

最后一帧的状态 animation-fill-mode：forwards 最后一帧 /backwards第一帧


播放状态 animation-play-state：running/paused暂停
```



练习：

作业1：

https://sc.chinaz.com/jiaobendemo.aspx?downloadid=0202185655711



作业2：

https://sc.chinaz.com/jiaobendemo.aspx?downloadid=32021103235198