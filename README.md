# CatAndDog-SLGgame-by-Java
## 一、	实作题目
小型即时策略游戏

## 二、	开发过程
### 1.	设计流程
 
## 2.	实现方式
### 2.1	绘制游戏窗口
（1）	使用javax.swing.JPanel类绘制窗口

### 2.2	绘制角色
（1）	创建Role类，定义角色基本属性（width、height、x、y、hp等）<br>
（2）	使用java.awt类获取角色图片<br>
（3）	设置drawself方法来绘制攻击动作<br>

### 2.3	绘制游戏地图
（1）	使用java.awt类获取资源组件并加入窗口来绘制游戏背景图片
### 2.4	添加鼠标监听器
（1）	使用java.awt.event.KeyEvent类和java.awt.event.KeyListener类设置键盘监听器实现角色移动等功能

### 2.5	添加角色移动事件
（1）	通过判断是否在目的坐标来执行角色移动事件<br>
（2）	若角色不在目的坐标，通过赋予角色对应方向状态达到角色自动寻路到目的坐标<br>
（3）	若角色不被选中，则角色不响应鼠标操作<br>
（4）	到达目的坐标后，随机朝一个角度偏移20个像素，目的在于避免单位重叠，难以选中<br>

### 2.6	添加角色攻击动画
（1）	通过判断角色周围有无敌人来执行角色攻击动作<br>
（2）	若角色半径30像素内有敌人，则执行攻击动作<br>
（3）	被攻击的角色收到攻击绘制被攻击动画，且执行受到伤害方法<br>
（4）	选中单位周围敌人死亡或者远离则结束单位攻击动作，且被攻击单位停止执行收到伤害方法<br>

### 2.7	添加单位死亡事件
（1）	若单位hp低于0，则执行死亡方法<br>
（2）	将单位移出单位缓冲池<br>
### 3.	如何检查系统功能
由于实作项目仅为一个小型游戏，仅具有即时策略游戏的基本功能，功能较少且易判断，故启动游戏，进行人工测试即可。F1为生成己方单位，F2为生成敌方单位，鼠标右键移动，鼠标左键单击或拖拉选择单位，ESC键取消选择

## 三、	设计方案
### 1.	基本构架
 
从上至下依次是：监听器模块、模型模块、线程模块、视窗模块<br>
（1）	监听器模块：实现角色移动功能及选择单位功能<br>
（2）	模型模块：玩家角色、敌人的基本属性，如：hp、移动速度、攻击力、攻击范围、攻击速度等<br>
（3）	线程模块：绘制画面线程，绘制画面线程主要是控制游戏角色、敌人、攻击动画等图片的绘制<br>
（4）	视窗模块：绘制游戏角色、敌人等模型模块中的模型，搭配线程模块中的绘制画面线程可实现动态画面，即游戏化<br>

## 四、	技术讨论
### 1.	存在问题
（1）	作品仅为一个基本框架，内容单一、没有游戏性<br>
（2）	单位寻路算法较为简单，角色移动有些生硬<br>
（3）	单位碰撞问题未解决，仅通过限制地图和随机数等方法来避免<br>
（4）	敌人AI较为简单，仅会无目的地四处漫游<br>
### 2.	解决方法
（1）	可以添加更多的地图，控制单位、敌人单位，可以加入建筑生产系统，丰富游戏性<br>
（2）	著名的寻路算法有A*算法，可以将其融会贯通融入其中<br>
（3）	寻路算法可以有效地解决单位碰撞及地图碰撞问题<br>
（4）	敌人AI的提升需要策划多角度的考虑，例如可以给敌人透明化玩家当前的位置，这样敌人会显得更智能化更有进攻性。<br>
