# H5_questionnaire
H5问卷调查模板
公司最近有一个需求就是要在半天时间内产出一个H5调查问卷，所以此H5模板就诞生了。这个模板是我第一次写，目前里面应用了HTML5+css3来实现动画效果，zepto.js+touch.js来实现手指划动翻页，里面还有很多不完善和不十分妥的地方，我会不断改进，同时更新在git上，也作为自己学习的一个记录。

2016.8.31记录<br>
1.把每个section的positioin：relative改为absolute，这样在上一页做完一个动画下一页就会立刻跟上，不会出现白屏，之所以出现白屏是因为上一页的relative属性导致上页虽然视觉上从页面划走了但是它的原位置还保留着(详见position：relative属性与absolute的区别)。
2.把原animationBasic()方法改为animationBasic(direction)，通过增加一个参数的方法，往哪个方向划动就向animationBasic(direction)传参数(next,pre,left,right),并根据不同的方向给outPage和inPage这两个变量赋予不同的class类名，通过不同的class类名达到上下左右不同的划屏效果。
3.在animationBasic(direction)方法中添加是否在进行动画的判断，在当前页划出屏幕和下一页进入屏幕后使isAnimation=true，代表正在进行动画，在后面的setTimeout定时器中的最后使isAnimation=false,代表动画结束。并且要在swipe()事件中的goPage()方法前添加是否在进行动画的判断，这样就不会导致一个动画没有进行完就划屏产生动画混乱的情况。

2016.9.5记录<br>
1.添加音乐控制，初始时判断音乐是否是播放状态（paused），如果是则让<audio>的状态变为play(),则开始播放音乐。
2.完善数据获取。
3.当选中一个选项时不能再选择其他选项。方法是设置一个全局变量ischosen=false，在点击“是”和“否”的时候添加一个if判断，在ischosen=false的时候才可以点击选项，并且点击后要return chosen=true，这样才可以做到选中一个选项后另一个选项不可选择。
