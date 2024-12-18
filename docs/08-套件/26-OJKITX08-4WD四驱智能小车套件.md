# 4WD四驱智能小车套件

<img src="../img/OJKITX08/01.jpg" width=50% />

[点我购买](https://item.taobao.com/item.htm?id=571721414420)

## 电机驱动系统

想要让小车运动起来，需要将电能转化为机械能，最后成为小车的动能。小车的动能是由4个直流电机提供的，而控制电动机运动的是一个电机驱动模块，模块与Arduino uno或其他控制器相连，负责接收信号去驱使电机运动，当然中间不可缺少的是要给驱动模块提供足够的电能，在4驱小车中，所有的电能都由两节18650锂电池提供，这一套系统被成为电机驱动系统。

在小车底盘搭建好以后（小车底盘搭建的方法请先参考<https://pan.baidu.com/s/1CAalZOXHZg54RPAB9tlcaQ>），我们首先需要搭建起来的就是电机驱动系统。

<img src="../img/OJKITX08/02.png" width=50% />

为了让后面的测试工作更方便，我们首先介绍如何将一些基本的传感器安装到底板上，首先准备好循迹传感器和避障传感器，以及固定传感器的4颗M3*10螺丝和螺母，如下图所示。

<img src="../img/OJKITX08/03.jpg" width=50% />

将循迹传感器安装到底板的孔中，并用M3*10螺丝固定。

<img src="../img/OJKITX08/04.jpg" width=50% />

<img src="../img/OJKITX08/05.jpg" width=50% />

<img src="../img/OJKITX08/06.jpg" width=50% />

<img src="../img/OJKITX08/07.jpg" width=50% />

再将避障传感器固定，方法如图示。

<img src="../img/OJKITX08/08.jpg" width=50% />

<img src="../img/OJKITX08/09.jpg" width=50% />

<img src="../img/OJKITX08/10.jpg" width=50% />

<img src="../img/OJKITX08/11.jpg" width=50% />

用3P排线与传感器连接，注意黑线一般为负极，对应传感器的“-”标号位置，白线一般为信号，对应传感器的“OUT”标号位置。

<img src="../img/OJKITX08/12.jpg" width=50% />

<img src="../img/OJKITX08/13.jpg" width=50% />

固定电机驱动板，注意电机驱动板需要用尼龙隔离柱做为支撑。

将电机的动力线与驱动连接，注意驱动板有三组的输出端口，两位的输出端口每一组管理同一个方向的电机，所以需要将一端的两个电机的统一个极同时接到一个孔中，并用M2.5*12螺丝固定紧，如图示。（此步骤需要着重注意，电机接好后，用手快速的扭转车轮，此时同侧的电机也会被感应产生的电流带动旋转，如果旋转方向与扭转方向相同，说明安装无误。如果不转，说明电机线接触不良，请重新固定电机线。如果旋转方向相反，说明接反电机线，请交换反转的电机线后固定。接好后请严格按照文字叙述的检测方法验证，图中的接线颜色不能说明接线一定正确。）

用母对母的杜邦线链接到电机驱动板的排针上，并记录杜邦线颜色与之对应的引脚标号。

<img src="../img/OJKITX08/14.jpg" width=50% />

固定18650电池盒，需要使用M3沉头螺丝，如图示。

<img src="../img/OJKITX08/15.jpg" width=50% />

<img src="../img/OJKITX08/16.jpg" width=50% />

<img src="../img/OJKITX08/17.jpg" width=50% />

把电池盒引出的线与免焊接DC头相连接，注意红色为正极，与“+”相连接，黑色为负极，与“-”相连接，接错可能导致控制板烧毁吗，此步骤切记在未安装电池的状态下操作，不可带点操作！

<img src="../img/OJKITX08/18.jpg" width=50% />

<img src="../img/OJKITX08/19.jpg" width=50% />

将下面所有的线束穿过上盖板的通孔中。

<img src="../img/OJKITX08/20.jpg" width=50% />

DC电源头从下面的通孔中穿出。

<img src="../img/OJKITX08/21.jpg" width=50% />

固定上盖板的M3*6螺丝。

<img src="../img/OJKITX08/22.jpg" width=50% />

将传感器扩展板与Arduino UNO控制器相连接。

<img src="../img/OJKITX08/23.jpg" width=50% />

将DC电源头插入到控制器。

<img src="../img/OJKITX08/24.jpg" width=50% />

如果选配了电压表，将电压表安装到上盖板的方孔中。

<img src="../img/OJKITX08/25.jpg" width=50% />

使用一根电源线将DC电源头的“+”与传感器扩展板的EVCC引脚相连接。

<img src="../img/OJKITX08/26.jpg" width=50% />

<img src="../img/OJKITX08/27.jpg" width=50% />

再将电压表的红色线与传感器扩展板的EVCC相连，黑色线与传感器扩展板的GND相连，通常情况下红线一般代表正极，黑色为负极。

<img src="../img/OJKITX08/28.jpg" width=50% />

现在，将电机驱动板引出的杜邦线，按照下面的对应关系连接到传感器扩展板上。

<img src="../img/OJKITX08/29.png" width=50% />

这是示例代码中的定义，一般情况下不允许修改，第一组字母与数字为驱动板上引脚的标号，第二组数字为传感器扩展板上的标号，用杜邦线连接，电机驱动板的+12v与DC插头的+相连接，GND与任意黑色底座的插针相连接，+5v与任意红色底座相连接（传感器扩展板白色底座插针为信号，红色底座均为电压为5v的VCC，黑色为GND。）如图所示。

<img src="../img/OJKITX08/30.jpg" width=50% />

<img src="../img/OJKITX08/31.jpg" width=50% />

将传感器引出的3P线与传感器扩展板相连。

<img src="../img/OJKITX08/32.jpg" width=50% />

<img src="../img/OJKITX08/33.jpg" width=50% />

如果选配了小车开关，需要将开关按入到上盖板的安装孔中，然后将电池盒引出的黑色线剪断，将剪断的两节线与开关的两根引脚焊接起来，需要使用电烙铁，产品不含焊接工具！

<img src="../img/OJKITX08/34.jpg" width=50% />

<img src="../img/OJKITX08/35.jpg" width=50% />

<img src="../img/OJKITX08/36.jpg" width=50% />

舵机的安装，将舵机放入对应的安装孔中，用舵机包内的自攻螺丝固定。

<img src="../img/OJKITX08/37.jpg" width=50% />

<img src="../img/OJKITX08/38.jpg" width=50% />

安装舵盘，将舵机转转到左右两极限后，找到一个与中间位置垂直的方向安装舵盘，然后用舵机包内的小螺丝固定好。

<img src="../img/OJKITX08/39.jpg" width=50% />

<img src="../img/OJKITX08/40.jpg" width=50% />

将舵机线与传感器扩展板相连接，橘黄色为信号部分，连接到传感器扩展板的12号口。

<img src="../img/OJKITX08/41.jpg" width=50% />

将超声波支架安装到舵盘上，使用M2.2自攻螺丝固定。

<img src="../img/OJKITX08/42.jpg" width=50% />

安装超声波传感器，且用母对母杜邦线连接。

<img src="../img/OJKITX08/43.jpg" width=50% />

<img src="../img/OJKITX08/44.jpg" width=50% />

接线的方法参考下图，超声波传感器的VCC与传感器扩展板的任意红色底座引脚相连，GND与任意黑色底座引脚相连。

<img src="../img/OJKITX08/45.png" width=50% />

<img src="../img/OJKITX08/46.jpg" width=50% />

<img src="../img/OJKITX08/47.jpg" width=50% />

若选配了蓝牙，将蓝牙模块直接插入到传感器扩展板上即可。需要注意的是，在烧录程序到小车的时候因为串口被蓝牙模块占用，故烧录程序的过程中需要将蓝牙模块取下，否则烧录程序不成功，其他占用串口的传感器亦是如此。

<img src="../img/OJKITX08/48.jpg" width=50% />

若选配了激光雷达，则先安装用尼龙住，M3*6螺丝固定到上盖板上。

<img src="../img/OJKITX08/49.jpg" width=50% />

将激光雷达与激光雷达底座连接，需使用尼龙隔离柱。

<img src="../img/OJKITX08/50.jpg" width=50% />

 将激光雷达底座与尼龙支架使用M3*6螺丝固定。

<img src="../img/OJKITX08/51.jpg" width=50% />

使用公对母杜邦线将激光雷达的接线引出，链接对应的引脚请参考对应激光雷达的使用手册以及示例代码，在这里不做解释。

<img src="../img/OJKITX08/52.jpg" width=50% />

<img src="../img/OJKITX08/53.jpg" width=50% />

<img src="../img/OJKITX08/54.jpg" width=50% />

<img src="../img/OJKITX08/55.jpg" width=50% />

安装完成后，安装电池，在这之前请确保线路没有短路的情况，否则可能 引发线路着火或电池爆炸。

<img src="../img/OJKITX08/56.jpg" width=50% />

## 红外循迹传感器的使用

红外巡线传感器模块的原理是利用红外对管检测自己发出的红外线对反射光（深色反射弱，浅色反射强）。寻线传感器可以帮助你的机器人进行白线或者黑线的跟踪，可以检测白底中的黑线，也可以检测黑底中的白线，检测到黑线返回低电平。是光电寻线机器人的必备传感器。

<img src="../img/OJKITX08/57.jpg" width=50% />

循迹传感器输出的信号为数字信号，黑线为低电平，白线为高电平，一般情况下，循迹使用黑色电工胶布贴在地面使用，或印刷地图作为循迹传感器捕捉的目标，但需要注意的是，瓷砖因为镜面反射过强，可能会导致传感器效果不佳。

<img src="../img/OJKITX08/58.jpg" width=50% />

（图片来源于网络，侵删。）

此小车循迹传感器的设计方案为两路巡线均在线上时，则前进，巡线示例程序请访问：<https://github.com/vyuke/4WD_Bot/blob/master/4WD_line_tracking/4WD_line_tracking.ino>

上传此程序到小车，即可实现巡线功能，如果发现巡线异常，请用螺丝刀调节巡线传感器上蓝色的电位器，调节探测灵敏度。

## 红外避障传感器的使用

<img src="../img/OJKITX08/59.jpg" width=50% />

传感器发射红外线,根据反射红外光探测前方障碍物，无障碍物时输出高电平,有障碍时输出低电平，在信号输出同时有指示灯指示状态，无障碍物时LED为绿，有障碍物时为红。同时内置38Khz信号发生器，通过调节蓝色的电位器可以改变传感器的探测范围，与循迹传感器使用方法相似，小车墙壁后改变行驶的轨迹，躲避障碍，需要注意，此传感器不可在阳光直射下使用，会导致传感器。

红外避障的示例程序请参考： <https://github.com/vyuke/4WD_Bot/blob/master/4WD_IR_Switch/4WD_IR_Switch.ino>

## 超声波避障传感器的使用

<img src="../img/OJKITX08/60.jpg" width=50% />

感器是利用超声波的特性研制而成的传感器。SR04是最常见的超声波传感器之一，在arduino开发中超声波传感器SR04主要用来测距，相比其他测距传感器有着简单易用、灵敏度高等特点。对于超声波传感器各种特性，超声波检测广泛应用在工业、国防、生物医学等方面。

超声波传感器的工作原理是首先发出一段特定的超声波信号，由于声音的反射特性，遇到障碍物后超声波传感器会收到回声，声音在空气中的传播速度是已知的，所以我们通过计算传感器两个波之间的时间差，通过公式就可以算出障碍物的距离。

我们的小车设计思路是，把超声波传感器安装在舵机的支架上，舵机可以让超声波传感器的头指向特定的方向，可以判断前、左、右的距离，这样小车能大致获得目前位置的情况，找到通道。并向宽阔的区域驶去。

超声波传感器使用的示例程序请访问： <https://github.com/vyuke/4WD_Bot/blob/master/4WD_sonar/4WD_sonar.ino>

## 蓝牙遥控

在这里的示例中，我们的蓝牙遥控是通过手机APP去实现的，蓝牙遥控包括但不限于使用手机APP进行遥控。

使用蓝牙遥控我们首先需要下载蓝牙控制APP，在这里使用IOS平台作为演示，登陆APP store，搜索blinker。

<img src="../img/OJKITX08/61.png" width=50% />

打开APP，首先添加需要接入的硬件，点击右上方的+号，已经接入过的设备会显示在图中。

<img src="../img/OJKITX08/62.png" width=50% />

点击Arduino。

<img src="../img/OJKITX08/63.png" width=50% />

点击蓝牙接入。

<img src="../img/OJKITX08/64.jpg" width=50% />

此时APP会开始搜索附近的蓝牙设备，所以小车需要在通电状态下。

<img src="../img/OJKITX08/65.png" width=50% />

如果蓝牙正常会搜到类似这样的一个结果。

<img src="../img/OJKITX08/66.png" width=50% />

点击连接。

<img src="../img/OJKITX08/67.png" width=50% />

点击编辑按钮，来设计我们的设备界面


<img src="../img/OJKITX08/68.png" width=50% />

<img src="../img/OJKITX08/69.jpg" width=50% />

我们加入几个按键模块来控制小车的方向，再添加一个监视器来查看小车返回的消息，方便调试。

编辑数据键名改为我们程序所写的键名

<img src="../img/OJKITX08/70.jpg" width=50% />

编辑完成后点击右上角的锁定按钮，既可以开始操作。

当然在小车目前没有烧录对应程序的情况下不会有反应，所以我们需要拔掉蓝牙模块烧录对应的示例程序。

示例程序请参考： <https://pan.baidu.com/s/1VlwFpmtszidtQnoqYiXN7w> 提取码: d423 

## 光雷达传感器的使用

<img src="../img/OJKITX08/71.png" width=50% />

激光雷达由一个旋转的三角测距仪组成，通过连续旋转并测量距离可以得出以雷达为圆心，周围的若干点的距离，如果把这个数据在极坐标系中绘制出来，可以看到一个二维的地图，如果计算机获得了空间的地图，那么让机器人的定位实现了可能，这就是应用前景巨大的SLAM (simultaneous localization and mapping),也称为CML (Concurrent Mapping and Localization)。在未来实现人工智能，万物互联的世界，SLAM起了重要的作用。

<img src="../img/OJKITX08/72.jpg" width=50% />

SLAM技术由于起复杂程度较高，我们不在此文中参数，激光雷达相关的资料以及SDK请访问： <ttp://www.slamtec.com/cn/Lidar/A1>

4WD小车使用激光雷达避障的示例程序请访问： <https://github.com/vyuke/4WD_Bot/blob/master/4WD_laser_radar/4WD_laser_radar.ino>

（注意：次示例程序只做简单的原理演示，并不能达到良好的避障效果，非产品质量以及性能问题！）