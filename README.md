ememeddoctor
============

#技术记录
---

##Android 

###开源库使用心得

 * EventBus 一个事件分发库

   [源码地址][1]

 * Volley 库使用
   [volley框架源码解析][2]

###开发技巧（及一些坑）
 * HttpClient会随机报出ConnectTimeoutException，弃用。4.0之后改用HttpUrlConnection会更好。其实Volley底层就是集合了这两货


 [1]:https://github.com/greenrobot/EventBus
 [2]:http://tomkeyzhang.duapp.com/?p=7
