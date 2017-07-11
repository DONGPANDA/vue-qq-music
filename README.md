# QQ-music日志
## recommond
### 拉取数据
```
npm install jsonp --save
```
[jsonp地址](https://github.com/webmodules/jsonp)
> 对jsop插件进行一次封装,来获取数据,主要是处理url和传入的参数,并且指定callback

### 图片挂载问题
> 设置了图片的样式和slider的宽度以后 图片的大小没有变化还是很大  

- 在slider组件中,我是在mounted这个钩子函数中执行setSliderWidth这个函数设置轮播总长度和给slider-item添加class
- 而在recommond中我获取数据是在created这个初始化完成的钩子中获取,在created时候获取是为了保证后面挂载的正常进行,但是其实获取数据的过程是需要时间的
- 也就是说在我进行mounted这一步的时候,我的数据可能还没get回来,slider里面并没有元素,即使数据获取回来后,mouted已经结束,所以样式未添加上
如图:
![改前](./debugPic/style2.png)

![改后](./debugPic/style1.png)


