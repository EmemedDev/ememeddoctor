ememeddoctor
============

#Android实践技术记录
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
  > * layout根标签可以尽量用<merge>来优化，布局层级多的可以尝试<ViewStub>按需加载，防止嵌套太深出现StackOverflowError，官方没有公布嵌套布局上限，不过一些低端机器，嵌套12-15层差不多就会报以上错误。

###Exception 流水（待考究）
 
 * lang.UnsupportedOperationException: Can't convert to dimension

     现象：父控件是FrameLayout 子控件有属性 android:layout_marginBottom="" 

 [1]:https://github.com/greenrobot/EventBus
 [2]:http://tomkeyzhang.duapp.com/?p=7
 [3]:https://code.google.com/p/google-gson/ 

##UI设计
 
### 基本标准
 * iPhone ： 57*57  114x114 （4s）
 * android：72*72 （hdpi）   128*128  （xhpi）

### 1.Launcher图标
图标的最佳宽高是48x48 dp。

ldpi:36*36px,0.75倍密度，一般不用提供，系统会从hdpi取图缩小1倍。
mdpi:48*48px, 1倍密度
hdpi:72*72px,1.5倍密度
xhdpi:96*96px,2倍密度
xxhdpi:144*144px，3倍密度

###2.Action Bar图标
图标的最佳宽高是32*32dp。

###3.小图标和上下文图标
图标的最佳宽高是16*16dp。

###4.通知图标
图标的最佳宽高是24*24dp。

###5.图标命名原则
Asset Type	Prefix	Example
Icons	ic_	ic_star.png
Launcher icons	ic_launcher	ic_launcher_calendar.png
Menu icons and Action Bar icons	ic_menu	ic_menu_archive.png
Status bar icons	ic_stat_notify	ic_stat_notify_msg.png
Tab icons	ic_tab	ic_tab_recent.png
Dialog icons	ic_dialog	ic_dialog_info.png
###6.无损压缩png图片，这个是减小资源图片大小的一个有效途径。
OptiPNG
http://optipng.sourceforge.net
Pngcrush
http://pmt.sourceforge.net/pngcrush/

   
