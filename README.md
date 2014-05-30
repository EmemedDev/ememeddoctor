ememeddoctor
============

#技术记录
---

##Android 

###开源库使用心得

 * EventBus 一个事件分发库,用于Activities, Fragments,和后台线程之间传递消息，开销据说较低

   [源码地址][1]

 * Volley 库使用
 * 
   [volley框架源码解析][2]

 * gson  解析json爆好用。不过有少少坑，例如实体要空构造，实体里数组用List不要用ArrayList否则报错。
   [https://code.google.com/p/google-gson/][3]

###开发技巧（及一些坑）
 * HttpClient会随机报出ConnectTimeoutException，弃用。4.0之后改用HttpUrlConnection会更好。其实Volley底层就是集合了这两货
 
 * UI性能优化
  > * ListView的每一项item的布局顶层尽量使用相对布局优于线性布局，减少布局层级。

###Exception 流水（待考究）
 * lang.UnsupportedOperationException: Can't convert to dimension: 
    现象：父控件是FrameLayout 子控件有属性 android:layout_marginBottom="" 

 [1]:https://github.com/greenrobot/EventBus
 [2]:http://tomkeyzhang.duapp.com/?p=7
 [3]:https://code.google.com/p/google-gson/ 

##UI设计
 
### icon标准
 * iPhone ： 57*57  114x114 （4s）
 * android：72*72 （hdpi）   128*128  （xhpi）
   
